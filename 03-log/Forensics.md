## Version Control
- Making sure there is a .git file in the repo, this ensures you can use git commands to view and extract information
- Git log ~ see what commits have been made
- Each commit has a githash and this can be seen by running git show <hash>
- Git branch, seeing all the branches
- Git checkout branchname, changing branches


- What is the email address of the employee who was compromised? 
    - gpeterson@mpd.hacknet.cityinthe.cloud 
- Each employee is assigned a flag. Which flag was compromised? (20 pts) 
    - -SKY-LRHX-4910 
- Greg thinks that he may have had additional account credentials that were compromised. What's the name of the service provider for that other compromised account? 
    - Facebook 
- What was the password on that compromised account? 
    - waffles85

## PDF 
- Using a tool like Metadatago can allow you to look for program names, PDF versions, and software used to redact information. 
- What is the name of the program that exported this PDF file? 
    - Adobe Photoshop
- What PDF version is this file?
    - 1.7
- What software was used to redact the file and insert a watermark? 
    - PDFTron 
- What is the flag? 
    - SKY-PDRD-2390

## File Craving
- The command `file` stores a list of magic bytes and the corresponding file formats, so running `file filename` will give you the correct file type.
- The command `binwalk` will show you if any other files are packaged inside the original file. 
- Using `man binwalk` will give you formatting options
- In this gym, use `binwalk --extract --dd “png:png” green_file` to find any other png files hidden inside the original file.
- You can check each file found with `file`, in this case, the file CAB is not an image file
- You can use `tar xvf CAB` to unpack the file, this will give you the file flag. 

## Magic Bytes
- When putting a file into cyberchef it tells you the initial bytes of the file, but in this case, the last byte is different, meaning the file was tampered with.
- Putting the file into `HexEd.it`, will let you change the byte of the file, change the first 8 bytes to `89 50 4E 47 0D 0A 1A 0A`
- You can replace the last 4 bytes from `49 46 00 0D` to `00 00 00 0D`, this is the file signature of an actual png file.
  
- What is the original file type?
      - png
- What is the flag?
      - SKY-DSFG-5792
  
## Docter
- We are giving a .docx file, but to be sure nothing else is packed into the file, we run `binwalk` on the file.
- We see that there is more to this than just .docx, so we `unzip` the file
- This will show you everything that was in the .docx file and where it has been placed after the unzip
- You see, there are 5 image files, open each one to see which one has a hidden message.
- What is the name of the hidden file containing the flag?
      - image0.png
- What is the flag?
      -  SKY-RATL-8439

## The Book
- Install volatility3 `singularity build $CONTAINERS/volatility3.sif docker://sk4la/volatility3`
- Creating a countainer `alias vol3="singularity exec $CONTAINERS/volatility3.sif volatility3"`
- To check where the dump was taken from, run `file filename`
      - Windows
- To check the name of the computer `vol3 -f ./memdump.mem windows.imageinfo`
- This will extract all the data that contains the computer name.
- To check which user is logged in run `vol3 -f ./memdump.mem windows.pstree` and `vol3 -f ./memdump.mem windows.pstree`
      - liber8hacker
- Running the command with `| grep liber8hacker` will allow you shorten your list of files and find the one that we are looking for `vol3 -f ./memdump.mem windows.filescan | grep liber8hacker`
      - Users\liber8hacker\Desktop\black_book.db
- Putting this command will allow you to extract all data `./vol.py -f ./memdump.mem -o ./output windows.dumpfiles.DumpFiles --virtaddr Users\liber8hacker\Desktop\black_book.db`
- You can install SQLite
-run
    -`sqlite3 output/black_book.db`
    - `.tables`
    - `SELECT * FROM book;` > Should give you the answer we are looking for
      - barbara|walters
- Then run `vol3 -f ./memdump.mem windows.hashdump` to get all the hashes
- Go to a site like `https://crackstation.net/` and paste the given NTLM hash, this will give you the password output. 
