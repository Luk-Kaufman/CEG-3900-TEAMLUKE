# Telnet Protocol Notes

Telnet is a network protocol used to provide **remote command-line communication** between a client and server over a TCP connection. It is one of the earliest remote terminal protocols and is largely considered insecure because it transmits data in **plaintext**.

---

## Purpose of Telnet
- Allows users to remotely access and control a machine.
- Sends keyboard input from client → server.
- Sends terminal output from server → client.

Because Telnet does not encrypt traffic:
- Credentials and commands can be easily captured using packet sniffing tools.

---

## Basic Communication Model
Telnet follows a simple client-server model:

Client:
- Connects to server using IP address and port.
- Sends commands as plain text.

Server:
- Executes or processes commands.
- Returns output text to client.

Typical port used:
- Port **23** (default Telnet port).

However, custom ports may also be used.

---

## Telnet Data Transmission
Telnet transmits data as:
- ASCII text
- Raw terminal control characters

This means:
- Commands appear readable in network captures.
- No encryption or hashing is applied.

---

## Packet Analysis of Telnet Traffic
When analyzing Telnet traffic in packet captures:

Look for:
- TCP streams containing readable text.
- Login prompts.
- Command execution sequences.

Useful Wireshark filters:
tcp.port == 23


Then:
- Follow TCP stream.
- View conversation as ASCII text.

---

## Authentication in Telnet
If authentication is used:
- Username and password are transmitted in plaintext.
- Can be easily extracted from packet captures.

This is why Telnet has largely been replaced by SSH.

---

## Security Risks of Telnet
Major risks include:

### Lack of Encryption
- Data can be intercepted easily.

### Credential Exposure
- Login information is not protected.

### Session Hijacking
- Attackers can capture and replay session traffic.

### Man-in-the-Middle Attacks
- Attackers can modify transmitted commands.

---

## Telnet vs Modern Protocols

Telnet:
- No encryption
- Plaintext communication
- Lightweight but insecure

SSH:
- Encrypted communication
- Uses cryptographic authentication
- More secure replacement for Telnet

---

## Common Telnet Commands
Inside a Telnet session:
open <ip> <port>: Connects to a server
quit: closes Session
help: Shows available commands

---

## How Telnet Appears in Packet Captures
When viewing Telnet traffic:

You may see:
- Login prompts
- Typed commands character-by-character
- Server responses in text form

This is because Telnet sends each keystroke individually.

---

