# SKY Log File (Binary CTF) Notes

The SKY Log File challenge involves analyzing a **custom binary file format** used to log network traffic. The goal is to parse raw binary data according to a provided specification to extract meaningful information.

---

## Why Is The Challenge Important?

This challenge provides:
- hands-on experience with **binary file parsing**
- practice interpreting **structured data formats**
- reinforcement of **low-level data handling**
- exposure to **CTF-style reverse engineering**
- understanding of how efficient logging formats work
- preparation for **forensics, reverse engineering, and security work**

---

## Concepts

### Binary File Parsing
- Reading raw bytes sequentially
- Following strict **file format specifications**
- Handling **big-endian integers**
- Tracking **byte offsets carefully**

---

### File Structure

#### Header
- Magic bytes (file identifier)
- Version
- Creation timestamp (Unix)
- Hostname (length + string)
- Flag (length + string, may be encoded)
- Number of entries

#### Body (Repeated Entries)
- Source IP (int → IPv4)
- Destination IP (int → IPv4)
- Timestamp (Unix)
- Bytes transferred

---

### Data Interpretation
- **Integers**: 4 bytes (big-endian)
- **Strings**: length-prefixed
- **Timestamps**: Unix → UTC
- **IP addresses**: int → dotted format
- **Flags**: may require decoding (e.g., Base64)

---

### Tools & Techniques
- `xxd` / `hexdump` for viewing binary
- Python (`struct`, `socket`, `datetime`) for parsing
- CyberChef for quick conversions
- Base64 decoding tools
- Careful byte-by-byte analysis

---

### Common Pitfalls
- Off-by-one **offset errors**
- Incorrect **endianness**
- Misinterpreting encoded fields
- Including extra bytes when extracting
- Over-relying on tools without verifying output

---

### Metrics Computed
- Total bytes transferred
- Unique IP addresses
- Top sender by data volume
- Bytes sent by top sender
- Busiest day (most traffic)

---

##  Takeaways
- Always **follow the spec exactly**
- Binary formats require **precision**
- Automating with scripts saves time and errors
- Validate results—CTFs often include **traps and edge cases**
- Understanding data at the byte level is a powerful skill

Questions

1. 
command: cat cff.sky | xxd
answer: sky-server-71

2.
find plaintext flag bytes: 55 30 74 5a 4c 56 42 42 55 6c 4d 74 4e 7a 4d 79 4e 51 3d 3d
answer: SKY-PARS-7325

3.
put file into given cyber chef template
Sat 3 March 2018 05:00:00 UTC
answer: 2018-03-03

4.
find num entries bytes: 00 00 00 a2
answer: 162

5.
use given cyberchef template and put in file
answer: 811167

6.
use given cyberchef template and put in file
answer: 13

7.
create the merged log by following the instructions in walkthrough
Use this command: awk '{sums[$1]+=$4} END {for (ip in sums) print sums[ip], ip}' merged.log  | sort -n
answer: 229.212.21.212

8. 
same command as 7
answer: 145048

9.
command: awk '{sums[$3]+=$4} END {for (date in sums) print sums[date], date}' merged.log  | sort -n
answer: 2018-03-23
