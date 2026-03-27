## Python 2
- Given a complied python file, are task is to find a password that the program will print. 
- We first need to decompile the .pyc file [uncomply2](https://github.com/Mysterie/uncompyle2)
- This will give us the following code
```
import sys

def main():
    if len(sys.argv) != 2:
        print 'Invalid args'
        return
    password = sys.argv[1]
    counter = 0
    vals = list('tfzbwlyzljylawhzzdvyk')
    if len(password) != len(vals):
        print 'incorrect'
        return
    while counter < len(password):
        x = ord(password[counter]) + 7
        if x > ord('z'):
            x -= 26
        if chr(x) != vals[counter]:
            print 'incorrect'
            return
        counter += 1

    print 'correct'

if __name__ == '__main__':
    main()

```
- First this we seee is that we are given a list 
- Second thing is that we have a +7, meaning we shift each letter by - 7
- T = M, F = Y, Z = S
- 1. What is a secret key that will pass validation?
    - mysupersecretpassword