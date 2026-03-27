## Python 3
- Given a compiled python file, our task is to find a password that the program will accept.
- We first need to decompile the .pyc file using [uncompyle6](https://github.com/rocky/python-uncompyle6)
- This will give us the following code:
```
import sys

def main():
    if len(sys.argv) != 2:
        print('Invalid args')
        return
    password = sys.argv[1]
    builder = 0
    for c in password:
        builder += ord(c)

    builder = builder << 2
    builder = ~builder
    builder = builder ^ 12648430
    builder = ~builder
    if builder == 12645638 and ord(password[0]) == 78 and len(password) == 11:
        print('correct')
    else:
        print('incorrect')

if __name__ == '__main__':
    main()
```

- Unlike Python 2, there is no simple character shift — instead the program sums the ASCII values of all characters and runs them through a chain of bitwise transformations
- There are three conditions that must all be true for the password to be accepted:
  1. `builder == 12645638` — the transformed sum must equal this value
  2. `ord(password[0]) == 78` — the first character must be `'N'` (ASCII 78)
  3. `len(password) == 11` — the password must be exactly 11 characters long

- To reverse the transformations we work backwards from the target value `12645638`:
```python
target = 12645638
temp = ~target          # undo the last ~
temp = temp ^ 12648430  # undo the XOR
temp = ~temp            # undo the first ~
totalUnicode = temp // 4  # undo the left shift << 2 (same as dividing by 4)
```

- This gives us the required total ASCII sum of all 11 characters = 698
- We know the first character is `'N'` (ASCII = 78), so the remaining 10 characters must sum to 620
- 620 ÷ 10 = 62, and `chr(62)` = `'>'`

- 1. What is a secret key that will pass validation?
  - `N>>>>>>>>>>`