## Encryption (RSA / GPG)
- Symmetric Encryption
  - 128-bit CBC
    - Encrypt `openssl enc -aes-128-cbc -in tux-96.png -out tux_cbc.enc`
    - Decrypt `openssl enc -aes-128-cbc -d -in tux_cbc.enc -out tux_cbc.png`
    - While using CBC, images look static, kinda like a TV
  - 128-bit ECB
    - Encrypt `openssl enc -aes-128-ecb -in tux-96.png -out tux_ecb.enc`
    - Decrypt `openssl enc -aes-128-ecb -d -in tux_ecb.enc -out tux_ecb.png`
    - While using ECB, you will still be able to see the image, it will just be a different color. 
  - 128-bit OFB
    - Encrypt `openssl enc -aes-128-ofb -in tux-96.png -out tux_ofb.enc`
    - Decrypt `openssl enc -aes-128-ofb -d -in tux_ofb.enc -out tux_ofb.png`
    - While using OFB, images look similar to CBC, but don't look like static.
- RSA
  - In order for RSA work, you must have a public key, which is used for encrypting data, and a private key, which is used to decrypt data. You must need both since RSA is an asymmetric encryption algorithm.
  - RSA Broken Down:
    - What is given
    1. c = Ciphertext
    2. n = Part of the public Key
    3. e = Part of the Public Key
    - What we need to have:
    5. d = Part of the Private Key
    6. p = Part of the Private Key
    7. q = Part of the Private Key
    8. m = The plainext message
  - Equations Needed:
    1. n = p * q
    2. d * e = 1 mod (p - 1)(q - 1)
    3. m = c^d (mod n)
  - Example:
    - Equation 1: n = 1079, consisting of a large prime number and a small prime number and only two values multiply to 1079, 83 and 13. Again must be prime numbers. 
      - `1079=83*13`
    - For this part, you'll need a scientific or RSA calculator
    - Equation 2: e = 43, p = 83, q = 13, from here you can use basic PEMDAS
       - `d * 43 = 1 mod (83-1)(13-1)`
       - `d = 43^-1 mod 984`
       - `d = 595`
    - Now you have all the values except m.
    - Equation 3: c = 996 894 379 631 894 82 379 852 631 677 677 194 893, d = 595, n = 1079
    - You'll notice our c (Cipher text) has a range of numbers, so each number will get plugged into c.
      - `m = 996^595 (mod 1079)`
      - `m = 83`
    - Now, by using the ASCII table, you can convert the number into plain text.
      - `m = 83 = S`
    - You must do this for all numbers in the ciphertext. 
- Thunderbird
  - Thunderbird is a free, open-source email client that focuses on security and user control.
  - Thunderbird stores emails, folders, and attachments on your own devices.
  - Thunderbird makes sure only you and the recipient can see a sent email, with end-to-end encryption. 
- Links
  - `https://personal.utdallas.edu/~muratk/courses/crypto09s_files/modes.pdf`
  - `https://www.encryptionconsulting.com/education-center/what-is-rsa/`
  - RSA Calculator `https://www.tausquared.net/pages/ctf/rsa.html`
  - Prime Number Calculator `https://www.calculator.net/factor-calculator.html`
  - Thunderbird Download `https://www.thunderbird.net/en-US/thunderbird/all/`
