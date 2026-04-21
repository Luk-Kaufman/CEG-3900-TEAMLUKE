# Pandora Custom Protocol Notes

## Overview
Pandora is a custom encrypted-style communication protocol used between a client and server. The goal of protocol analysis is to understand message structure by inspecting packet captures (.pcap files).

The capture contains:
- SSH traffic
- HTTP traffic
- Custom protocol traffic

Filtering is required to isolate the custom protocol communication.

---

## Communication Model

The protocol follows a **3-stage communication process**:

### 1. Initialization Phase
Client tells the server how many hash requests will follow.

### 2. Request Phase
Client sends multiple hash requests containing:
- Integrity check value
- Length of data
- Data payload

### 3. Response Phase
Server sends:
- Total length of hash data
- Concatenated hash results for each request

Hashes are returned in the same order as requests.

---

## Packet Filtering

To isolate protocol traffic in Wireshark:


tcp && !(tcp.port == 22) && !(tcp.port == 80)


Then:
- Find first TCP stream packet
- Follow TCP stream
- View data as hex dump or ASCII

---

## Message Format Details

### Initialization Message (Client → Server)

Structure:

N (4 bytes)


Meaning:
- 4-byte integer
- Network byte order (big-endian)
- Represents number of hash requests

Example:
- Client sends **5 requests**

---

### Hash Request Message (Client → Server)

Structure:

Check (2 bytes)
Length (4 bytes)
Data (variable length)


Check Field:
- 2-byte magic validation value
- Appears repeatedly in stream
- Example magic ID: 0x0417

Length Field:
- 4-byte integer
- Specifies data payload size in bytes

Example lengths observed:
- First request → 0x58 = 88 bytes
- Second request → 0x48 = 72 bytes

Data Field:
- Payload to be processed
- Often base64 encoded
- One of these requests contains hidden information

---

### Hash Response Message (Server → Client)

Structure:

Count (4 bytes)
Hashes (concatenated fixed-size blocks)


Count:
- Total bytes of hash data following

Hashes:
- Concatenated hash outputs
- Same ordering as client requests

---

## Hash Size Calculation

Given:
- Total requests = 5
- Response size = 0xa0 = 160 bytes

Hash size calculation:

160 ÷ 5 = 32 bytes per hash


Therefore:
- Each hash chunk = 32 bytes
- First 32 bytes = Hash 1
- Next 32 bytes = Hash 2
- Continue sequentially

---

## Encoding / Decoding Concepts

### Network Byte Order
- Uses big-endian formatting
- Most significant byte first

### Hexadecimal Interpretation
Common conversions:
- 0x58 → 88
- 0x48 → 72
- 0xa0 → 160

### Base64 Encoding
- Some request data may be base64 encoded
- Decoding may reveal hidden messages or flags

---

## TCP Stream Analysis Steps

1. Apply protocol filter
2. Follow TCP stream
3. Switch to hex view
4. Identify message boundaries using protocol structure
5. Extract payloads for decoding

---

## Security Concepts Demonstrated

This protocol highlights:
- Custom protocol design
- Data serialization
- Structured packet parsing
- Reverse engineering techniques

---

## Lab Solution

1. Apply Wireshark filter for custom traffic, then check first packet’s destination IP (server) in the TCP stream/packet details.

2. Same filtered packet → check source IP of first client → server connection.

3. In TCP handshake (SYN/SYN-ACK), check destination port on server side (SYN-ACK response shows listening port).

4. Follow TCP stream → read first 4 bytes in hex → convert from network byte order (big-endian) to decimal.

5. Same initialization field “N” → directly shown as number of hash requests in stream.

6. In stream, first request’s Len field (4 bytes after check) → convert hex to decimal.

7. Same as #6 but for second request block (next “Len” field after second check ID).

8. In server response section, take total response size / number of hashes (or observe chunk splitting) → each chunk size is consistent → infer bytes per hash.

9. In response hex dump → take first 32-byte chunk of hash response.

10. In response hex dump → take second 32-byte chunk (next 32 bytes).

11. In TCP stream, find any request payload → copy data field → Base64 decode it to reveal flag.

1. 10.1.0.20
2. 10.1.0.217
3. 60123
4. 0x0417
5. 5
6. 88
7.72
8. 32
9. b8c97b08e198fa9ff79a3a9c1f0109b18687b7a1a3ff1772c29b4dc86753d711
10. 8817153ae81d94b5d6c745e63d1df31d5d02bd3b030b820c3c038654fdc619c
11. NCL-FJCG-1632
	
