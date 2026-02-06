## Cypher/crypto
- Cyberchef local install?
    - Going to Cyberchefs website and clicking the top left corner, but the website does not require local installation, but the option is given.
    - While all the features are given on the website, some may prefer to install a standalone copy of Cyberchef, which is now yours, and you can run it where the network may be segmented, or there is little to no internet connection. 
- Cyberchef notes
    - Cyberchef allows you to analyze and decode/encode data
    - Cyberchef has many encryption options, allowing you to encode/decode in many different ways
    - Cyberchef is fully "server-free," meaning that no inputs or outputs are saved or sent anywhere.
- quipquip notes
    - Quipqiup is a web-based tool used to solve substitution ciphers.
    - Quipqiup uses frequency analysis to decode encrypted text.
    - Quipqiup runs in the browser and does not require installation.
- Shift
    - Shift just means that the alphabet is shifted over a certain number. 
    - In this case, the shift is encrypted using ROT-13, ROT means rotated, and 13 means the letters are rotated 13 times, for example: A=N, B=O, C=P.
    - Something to remember is that the shift cipher is always the alphabet, but just shifted down.
      1. `Plaintext:      ABCDE     FGHIJK      LMNOP      QRSTUV     WXYZ`
      2. `Ciphertext:     NOPQR     STUVWX      YZABC      DEFGHI     JKLM`
    - iveghny ynxr = Virtual Lake
- French
    - French Cypher or Vigenère cipher, shifts plaintext letters based on corresponding letters in a repeated keyword.
    - For example, if you have a key of `qizkwcgqbs`, and you need to decode `Y ln`, you will need to find q on the left side of the table and find Y on the top side, and see where both meet up. In this case, they both meet up at I, so Q+Y=I, I+L=D, Z+N=O, I do.
    - Y ln xkv lubj swlzqvkht, A vmzb pjk bbua we ddgs ILQ-GQYU-8026 = I do not fear computers, I fear the lack of them SKY-QIZK-8026
    - One thing you might notice is that our key is shorter than our phrase. In that case, after the 10th letter, you would start over with Q again. For us, our 10th letter is S. Q+S=C. 
- Strings
    - String is a Linux program that can be used to find hidden messages in images.
    - Combining string and grep will allow grep to look for binary data that converts to characters resembling the standard flag format.
    - Most commonly, the command looks like this: `strings filename.jpg | grep SKY` - SKY here refers to what you're looking for.
    - `string filename.jpg` = This scans the JPG file and extracts human-readable text hidden inside the binary data.
    - `grep SKY` = Searches for words that match SKY.
- @Bash
    - @Bash is the same as atbash.
    - @Bash is an encryption method that is similar to shift, but in this case, the entire alphabet is reversed.
      1. `Plaintext:          ABCDE        FGHIJK     LMNOP     QRSTUV     WXYZ`
      2. `Ciphertext:         ZYXWV        UTSRQP     ONMLK     JIHGFE     DCBA`
    - Tools like the ones mentioned before can be used.
- Fencing
    - Fencing or rail fence cipher or zig-zag ciphers
    - While some encryption methods can encrypt the wording entirely, fencing only rearranges the letters.
    - For example, we have `THIS  IS  A  SECRET` and the Ciphertext `TATHSSEIIERSC`.
    - This can be shown as THISISASECRET, in a zig-zag pattern on a 4 by 13 board.
    - The reason why we got 4 is that it is the key to how many rows will be added, you can put any number. 
- Links
    - `https://quipqiup.com/`
    - `https://gchq.github.io/CyberChef/`
    - More advanced Cyberchef options `https://www.gaijin.at/en/infos/cyberchef`
    - This site allows you to do shifts of ROT-1 to ROT25 `https://rot13.com/`
    - Pretty good site that went into detail on Vigenere Cipher `https://www.omnicalculator.com/how-vigenere-cipher-works`
    - String help page `https://man7.org/linux/man-pages/man1/strings.1.html`
    - Fencing Site `https://crypto.interactive-maths.com/rail-fence-cipher.html`
