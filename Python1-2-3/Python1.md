## Python 1
- This challange involes reverse enginerring the piece of python code. 
- We are given a base code 
``` 
#!/usr/bin/python

import sys

def main():
  if len(sys.argv) != 2:
    print("Invalid args")
    return
  password = sys.argv[1]
  builder = 0
  for c in password:
    builder += ord(c)
  if builder == 1000 and len(password) == 10 and ord(password[1]) == 83:
    print("correct")
  else:
    print("incorrect")

if __name__ == "__main__":
  main()
```
- The Three Conditions

The program accepts a password only if **all three** are true:

| Condition | Meaning |
|---|---|
| `builder == 1000` | Sum of all ASCII values must equal **1000** |
| `len(password) == 10` | Password must be exactly **10 characters** |
| `ord(password[1]) == 83` | Second character must be **`'S'`** (ASCII 83) |


- Solving It

- Remaining sum after `'S'`: `1000 - 83 = 917` across 9 characters
- Fill with `'f'` (102), `'e'` (101), and `'g'` (103) to hit exactly 1000
- eSfffffgfe

| Char | e | S | f | f | f | f | f | g | f | e |
|------|---|---|---|---|---|---|---|---|---|---|
| ASCII | 101 | 83 | 102 | 102 | 102 | 102 | 102 | 103 | 102 | 101 |

- Total: 1000  — Length: 10  — `password[1]` = `'S'` **

- Run It
```bash
python python1.py eSfffffgfe
# Output: correct
```
- eSfffffgfe