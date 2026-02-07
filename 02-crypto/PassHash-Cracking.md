# Password/Hash Cracking Notes

The Cyber Skyline Trove guide on password cracking explains how password hashing works and why tools like Hashcat are effective at testing password strength. Since systems store hashes instead of plaintext passwords, recovering a password requires guessing possible inputs, hashing them, and comparing the results. Because many users choose predictable passwords, structured guessing strategies can be surprisingly effective. Tools such as John the Ripper serve a similar purpose and are widely used in cybersecurity education and defensive security testing.

---

## Why is this so important?

Understanding password cracking techniques is essential for defensive cybersecurity.

- Many real-world breaches succeed because of weak or reused passwords
- Security professionals use cracking tools to audit password strength
- Learning these methods helps organizations:
- Enforce better password policies
- Understand attacker techniques
- Improve hashing and authentication systems
- This knowledge should always be used ethically and with authorization.

---

## Concepts

### Password Hashing

- Systems store hashes, not plaintext passwords
- A hash is a one-way cryptographic output
- The same password always produces the same hash
- You cannot “reverse” a hash directly — you must guess inputs and compare hashes

### Hashcat

Hashcat is a high-performance password recovery tool often used in security testing.

#### Key ideas

- Designed to test large numbers of password guesses efficiently
- Works best when you understand:
    - Hash types
    - Password patterns
    - Human password behavior

#### Common attack styles

- Dictionary-based guessing – trying passwords from known lists
- Pattern-based guessing – targeting likely formats
- Combination strategies – blending words with predictable additions

### John the Ripper

John the Ripper is another well-known password auditing tool. It is best known for:
- Supporting many hash formats
- Being able to apply intelligent modifications to password guesses
- Being useful for both beginners and advanced security testers
- Word list-based testing
- Pattern-driven guessing
- Probabilistic password generation
John the Ripper is often used in academic environments and professional password audits.

### Wordlists

A wordlist is a collection of possible passwords used for testing.

- Sources of wordlists include
- Common passwords from past breaches
- Dictionary words
- Pop culture references
- Names, locations, hobbies, or themes relevant to a target environment

---

## Permutations & Variations

Password guesses often expand beyond a base word by applying predictable changes.

Common patterns include
- Adding numbers to the end
- Capitalizing the first letter
- Replacing letters with symbols (like “a” → “@”)
- Adding punctuation

Security tools can automate these variations to test how users modify simple words into passwords.

---

## Solutions

1. golduck
2. basculin
3. rotom
4. celebi
5. goldeen 
