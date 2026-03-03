# Bandit12

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 03-Mar-2026 
**SSH:** ssh bandit12@bandit.labs.overthewire.org -p 2220
**Password:** 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

--- 
```
Goal: The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
```

I start by looking at the file and also creating a tmp folder for myself

![](attachments/Pasted%20image%2020260303174945.png)

Since the file is a hexdump, I googled how to reverse a hexdump.


I use xxd to first convert the file from a hexdump to binary.

`xxd -r data.txt > data2.bin`

**-r : reverse**

after getting a bin file, I used `file data2.bin` to get more information about the file.

The following output was printed.
`data2.bin: gzip compressed data, was "data2.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 572`

Seems like gzip was used to compress the data.

I use `gunzip data2.bin` but I got an error

I use `mv data2.bin data2.gz` to change the suffix, then I run `gunzip data2.gz` which extracted the file to `data2`

Using `file data2` I again try to get more information about the file since I know from the goal that the file is compressed multiple times.

`data2: bzip2 compressed data, block size = 900k`

It appears that the file is compressed using `bzip2`, to decompress, I run `bzip2 -d data2`, the output is `data2.out` as I did not specify a name.

**-d = decompress**

using `file data2.out` again, I get more information.

`data2.out: gzip compressed data, was "data4.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 20480`

I again need to extract it using gunzip, but before that, I change the name again to `data2.gz`

`mv data2.out data2.gz`

`gunzip data2.gz`

Using file `data2` I get more information

`data2: POSIX tar archive (GNU)`

this time it seems like it is a tar file

I change the extension to a `.tar`

`mv data2 data2.tar`

Then extract using tar

`tar -xf data2.tar`

to get the file `data5.bin`

I use `file data5.bin` to get information

`data5.bin: POSIX tar archive (GNU)`

From this point on, I repeatedly checked what type of file it was using `file` command and then using the appropriate extract method to then finally get the password.
![](attachments/Pasted%20image%2020260303182604.png)
# Conclusion
I learnt multiple compression command, tar, gunzip. and also hexdumps and binary files.





