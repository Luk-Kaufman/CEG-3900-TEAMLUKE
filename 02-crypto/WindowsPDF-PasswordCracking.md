# Windows and PDF Password Cracking

Password cracking refers to techniques used to recover passwords from stored data (such as hashed passwords) or encrypted files (like PDFs). In cybersecurity, understanding how cracking works is valuable for defense: strengthening authentication, detecting weak passwords, and improving access controls. Two well‑known tools studied in academic contexts are John the Ripper and Ophcrack—each illustrating different cracking methodologies and use cases.

---

## Why is this important?

Studying password cracking helps cybersecurity students grasp
- How attackers attempt to break authentication
- Why strong passwords and secure hashing matter
- The differences between hash cracking and password recovery
- How to evaluate and mitigate password related vulnerabilities

This knowledge directly backs up the defense strategies such as password policies, multi-factor authentication, and secure password storage.

---

## Concepts

*Hashes vs. Plaintext*

Passwords are often stored as hashes—one‑way mathematical transformations. Cracking is attempting to find the original input that produced the stored hash.

Attack types include:
- Brute force attacks which try every possible combination
- Dictionary attacks which try words and common variants from a list
- Rainbow tables which are pre-computed tables that map hashes to plaintexts
- Rule-based attacks which use patterns to make smarter guesses (e.g. replacing e with 3 or a with @)

## Windows password storage
- Older Windows used LAN Manager hashes which were weak and easily crackable.
- Newer versions use NTLM hashes which are stronger but still crackable with the right tools.

*PDF Encryption*
PDFs can be encrypted with user and owner passwords. Recovery tools target encrypted content by attempting to guess the password that unlocks the file, based on known encryption formats.

### John the Ripper

John the Ripper is another well-known password auditing tool.

It is best known for:
- Supporting many hash formats
- Being able to apply intelligent modifications to password guesses
- Being useful for both beginners and advanced security testers
- Word list-based testing
- Pattern-driven guessing
- Probabilistic password generation
John the Ripper is often used in academic environments and professional password audits.

### Ophcrack

Ophcrack is a tool specifically known for cracking Windows password hashes using rainbow tables.

- Rainbow tables are pre‑computed tables that map hash values back to possible plaintexts. They trade storage space for faster lookup.
- Windows focus is especially effective against older Windows LM hashes due to their small keyspace and simplistic hashing.
- Graphical emphasis: often packaged with a GUI and distributed tables, making it accessible for demonstration and teaching.
- Limitations:
    - Larger, modern hash types can be much harder.
    - Requires access to hashes.
- This gives educational value through demonstrating how pre‑computation can speed up cracking and why salting and modern hashing schemes reduce the effectiveness of such tables.
- This is useful in defense thinking because it shows why disabled LM hashing and strong password policies significantly increase security.

---
