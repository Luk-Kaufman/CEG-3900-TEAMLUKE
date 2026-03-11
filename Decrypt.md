## Decrypt
- HTTPS - the `s` it stands for secure, and it uses the TLS/SSL protocol to achieve its security.
- HTTPS uses encryption through:
  - Transport Layer Security (TLS)
  - Formerly Secure Sockets Layer (SSL
- Tools used: Wireshark
- You can open packets in Wireshark and load the SSL key log, Edit > Preferences
- Once you have protocols open, select `TLS`.
- Once in TLS, select the file under `(Pre)-Master-Secret log filename`
- Once you've done this, you can now exit that page and, in the main page, right-click> Follow > TLS Stream
1. What Cipher Suite was chosen by the secure socket server?
    - TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
2. What is the domain covered by the SSL key?
    - tomsvacations.com
3. What is the flag transferred over HTTPS?
    - SKY-LADN-1435
