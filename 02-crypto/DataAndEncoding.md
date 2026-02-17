* Data and encoding
  * `base64` encode and decode (can you do it similar to above for `xxd` inside vim?)
     * to encode a file use 'base64 input-file.txt > output-file.txt'
     * to decode a file use 'base64 -d encoded-file.txt > decoded-file.txt'
     * to encode a phrase use 'echo "Foo" | base64'
     * to decode a phrase use 'echo "SG93ZHkK" | base64 -d'
     * to encode using xxd open the file you want to edit vim file-name
        * start an xxd buffer in vim :%!xxd then edit the hex values
        * save and exit vim using :wq and use above encoding steps
        * to reverse the xxd use :%!xxd -r
  * `strings` gym for week 2
    * find out how to view the challenge flag via given the above `vim` tips to view the image as hex
      * the command 'strings "FILE" | grep "Text to look for"' can be used to find flags
* side challenge on a linux only system:
    * cleanly format a USB drive
        * identify USB with `lsblk` and format partition using `sudo mkfs.ext4 /dev/sdb1` (double-check device name)
    * mount it and make a text file with some unique known contents
        * mount with `sudo mount /dev/sdb1 /mnt/usb` then create file:
          `echo "UNIQUE_SECRET_123" > /mnt/usb/test.txt`
    * delete the text file using `rm`
        * remove normally with `rm /mnt/usb/test.txt` (data still exists on disk until overwritten)
    * unmount the drive (but still leave it attached so it is in `/dev`)
        * unmount safely using `sudo umount /mnt/usb` so filesystem is not in use
    * run `strings` on the USB drive hardware device directly: ie. `sudo strings /dev/sdb`
        * run `sudo strings /dev/sdb | grep UNIQUE` to recover deleted text from raw device  
* Other challenge working with encryption person:
    * take the encrypted `tux.png` (from your encryption person) and find out how to use
      `dd` or `vim` with `xxd` (above) and overwrite JUST the bytes of the image
      that correspond to the `.png` header and meta data, take this data from the original `tux.png`.  Then rename the encrypted file
      as a .png and view it in an image viewer.
      * To do this the first line needs to be replaced with the correct magic bytes, which for a png are 89 50 4E 47 0D 0A 1A 0A
    * document this header / file carving process
      * Use :%xxd
