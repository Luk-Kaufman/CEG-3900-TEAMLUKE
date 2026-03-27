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
