## Packet Dissection
Dissecting an IP packet header to understand how the protocol works
Interpreting data using the raw binary of an IP packet
Understanding IPv4 header format
   - The first 8 bits > 0, 1, 2, 3, 4, 5, 6, 7 > 8 bits make 1 byte
   - The first 4 bits > 0, 1, 2, 3 > Version 
   - The last 4 btits > 4, 5, 6, 7 > IHL
Guide
1.
   - Header checksum is 2 bytes long, starting at 10 bytes
   - Using a tool like cyberchef convert from Binary to Hex 
   - `4f 93`
2. 
   - TTL > Time to Live > 1 Byte > Starts at an offset of 8 Bytes
   - Using a tool like cybersef convert from Binary to Decimal 
   - `64`
3. 
   - To find the source IP you would look at the offset of the 12 btye
   - Putting the 12 btye from 0-3 and converting from Binary to Hex and changing IP format, > Input Hex > Output format Dotted Decimal
   - `192.168.128.128`
4. 
   - To find the destination IP you would look at the offset of the 16 btye
   - Putting the 62 btye from 0-3 and converting from Binary to Hex and changing IP format, > Input Hex > Output format Dotted Decimal
   - `159.203.96.154`
