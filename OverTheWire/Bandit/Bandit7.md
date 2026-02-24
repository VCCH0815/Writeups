# Bandit 7

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 24-Feb-2026 
**SSH:** ssh bandit7@bandit.labs.overthewire.org -p 2220
**Password:** morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

--- 
```
The password for the next level is stored in the file **data.txt** next to the word **millionth**
```

I assume this level I will have to use grep. [Grep](#Grep) is used to search for patterns in a file, in this case, the password is next to millionth, so I run.

`grep millionth data.txt`

![](attachments/Pasted%20image%2020260224142306.png)

# References
#### Grep
https://man7.org/linux/man-pages/man1/grep.1.html