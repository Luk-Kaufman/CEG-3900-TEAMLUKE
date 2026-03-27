# FTP Traffic Notes

File Transfer Protocol (FTP) is a standard network protocol used to transfer files between a client and a server over a TCP/IP network. FTP operates on a client-server model and can run in either active or passive mode. This changes how connections are made. It uses a control channel for commands and responses, and a data channel for transferring files. Even though this is popular for file sharing and website management, FTP is insecure because it transmits data in plaintext. Modern substitutes such as SFTP and FTPS provide encryption to mitigate these risks.

---

## Why is this important?

FTP is very important because it:

- facilitates reliable transfer of files across networks
- is important for website hosting, server management, and backup processes
- helps network administrators monitor large file movements
- offers a basic understanding of network protocols for cybersecurity analysis
- supports troubleshooting of network performance and data transfer issues

---

## Concepts

1. FTP Modes

Active Mode:
- Client opens a port and waits for the server to connect back for data transfer.
- Can be blocked by firewalls due to incoming connection requirement.

Passive Mode:
- Server opens a port and waits for the client to connect for data transfer.
- More firewall-friendly, commonly used in modern networks.

2. FTP Channels

Control Channel (Port 21):
- Handles login, authentication, and command instructions.
Data Channel (Port 20 or dynamic ports):
- Handles actual file transfer

3. Authentication

FTP typically uses username and password credentials.
Anonymous FTP allows users to log in without an account, usually with limited access.

### Security Considerations

Data is transmitted in plaintext, vulnerable to sniffing attacks.
Variants like FTPS (FTP over SSL/TLS) and SFTP (SSH File Transfer Protocol) encrypt data.
Strong passwords and firewall configurations are critical.

### Common Commands

1. `GET` / `RETR` – Download a file from the server.
2. `PUT` / `STOR` – Upload a file to the server.
3. `LIST` – List files in a directory.
4. `DELETE` – Remove a file from the server.
5. `PWD` – Show current directory on the server.

### Monitoring FTP Traffic

Network administrators can monitor FTP traffic to:
- Detect unauthorized access attempts.
- Track large file transfers.
- Identify potential data exfiltration
Tools like Wireshark can capture and analyze FTP packets

---

## Lab Solutions

1. user1:cyberskyline
2. FileZilla Server 0.9.53 beta
3. user1:metropolis
4. LIST
5. bank.cap
6. compcodes.zip
7. 28183 bytes
8. compcodes.zip
