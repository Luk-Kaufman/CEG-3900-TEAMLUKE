- Lookup
  - DNS and authorship
    1. The DNSKEY record holds the DNSSEC public signing key. As described in RFC 4034, Section 2, the DNSKEY resource record stores the public key that is used to verify DNSSEC signatures  for a DNS zone.
       - The DNSKEY Wire Format comprises a 2-octet flags field, 1 octet protocol field, 1 octet algorithm field, and a public key field.
       - Flag field, if bit 7 of the flag field has a value of 1, the DNSKEY record holds a DNS zone key.  If bit 7 has value 0, then the DNSKEY record holds some other type of DNS public key.
       - Protocol Field must have a value of 3, and anything other than 3 will be treated as invalid during signature verification.
       - Algorithm Field, identifies the public key's cryptographic algorithm and determines the format of the Public Key field.
       - Public Key Field holds the public key material
    2. The AAAA record is used to map hostnames to IPv6 addresses. According to RFC 3596, section 2, the AAAA resource record stores a 128-bit IPv6 address and provides the DNS extension that enables IPv6 address resolution. 
       - AAAA record type stores a single IPv6 address
       - AAAA data format, 128-bit IPv6 address encoded.
       - An AAAA query for a specified domain name will return all AAAA resource records.
       - Text format for AAAA `Hinden, R. and S. Deering, "Internet Protocol Version 6 (IPv6)
        Addressing Architecture", RFC 3513, April 2003.`
    3. The NS (Name Server) record is used to delegate a DNS zone. As described in RFC 1035, a DNS zone is delegated by listing the authoritative name servers for that zone using NS records. These records specify which DNS servers are responsible for answering queries for the delegated zone.
       - What is a nameserver? A nameserver is a type of DNS server that stores and provides DNS records for a domain. Most domains use multiple nameservers to improve reliability and availability, so if one nameserver fails, others can still respond to DNS queries.
