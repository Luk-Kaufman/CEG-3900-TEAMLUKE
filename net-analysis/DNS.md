# DNS NOTES

Domain Format System (DNS) is a critical part of the intranet's infrastructure that converts human readable domains to ip addresses that computers often use to identify each other on networks. It acts as the internet's phonebook which allows users to access websites without needing to memorize difficult numeric addresses. When someone puts in a URL in a browser (let's say google chrome for instance), a DNS query is created to ressolve the domain name to its respective IP address.

---

## Why Is DNS Important?

DNS
- allows people to access sites using domain names that are easy to remember instead of those long annoying ip addresses
- is important for the functionality of internet services such as web browsing, email sending, etc
- supports load balancing and redundancy, which improves website availability and reliability
- plays a critical role in network security. This includes DNS filtering and protection against attacks like DNS spoofing or cache poisoning
- leads scalable growth of the internet through offering a distributed and hierarchical naming system

---

## Concepts

- Domain Name: A human-readable address used to identify a website (e.g., jellymar.io).
- IP Address: A numeric identifier for a device on a network (e.g., IPv4: 192.168.1.1, IPv6: 2001:0db8::1).
- DNS Query: A request sent to a DNS server to resolve a domain name into an IP address.
- Recursive Resolver: A DNS server that receives queries from clients and takes responsibility for resolving the domain name fully.
- Authoritative Name Server
  - A server that provides the definitive answer for a domain’s IP address.
- Root Servers
  - Top-level DNS servers that direct queries to the appropriate TLD servers.
- TLD (Top-Level Domain) Servers
  - Servers responsible for domains like .com, .org, or country codes like .uk.
- Caching
  - Temporary storage of DNS query results to reduce latency and decrease server load.
- DNS Record Types
  - Different types of information stored in DNS
  - This includes A (IPv4 address), AAAA (IPv6 address), etc.
- Propagation
  - The process of DNS updates spreading across servers globally.

---

## Lab Solutions

1. AXFR
2. etas.com
3. 4 responses
4. TTL = 3600
5. 1.1.1.1
