## Gym Challange 
- NMAP is used to scan a target server, identify ports and services running on the machine
- Make sure not to run at home or at school without permission. 
- This was run on the airmanjoe server
- Command used 
1. Using `-p` you can specify the port range
2. Using `sU` to specify UDP post scans
3. `-sV` to determine the software version
4. `-Pn` > If the server blocks ping requests
5. Example: `nmap -p 1-1000 -sU -sV -Pn <target>`

- Lowest open TCP port
    - 7 
- Second lowest TCP port
    - 13 
- Third lowst TCP port 
    - 37
- Lowest UDP Port 
    - 7
- Software running
    - nginx

#### Airmanjoe Incomplete

- Flag 1
    - cat read.me
    - welcome~padawan
- Flag 2
    - 
- Flag 3
    -
- Flag 4
    - cat 'spaces in this filename'
    - low/orbit
- Flag 5 
    - cd hidden
    - ls -lah
    - cat .cantseeme
    - nananananananana+batman 
-  Flag 6
    - ./execute_me
    - calamity-zebra
- Flag 7
    - find -size 503c
    - honest$cap
- Flag 8
    - md5sum *
    - bravo-corgi
- Flag 9 
    - md5sum * 
    - echo-heeler
- Flag 10 