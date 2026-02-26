# Bandit9

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 26-Feb-2026
**SSH:** ssh bandit9@bandit.labs.overthewire.org -p 2220
**Password:** 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

--- 
```
Goal: The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
```

My first though was to use `grep` to get the strings

`grep "=*" data.txt` 

but it did not work.

![](attachments/Pasted%20image%2020260226204356.png)


Searching `grep binary file matches`, I found that since the file is binary, grep cannot process it correctly. To change this, I can add the `--text` option to treat the file as a text file to then grep for the strings.

![](attachments/Pasted%20image%2020260226204602.png)

# Conclusion
I learned that `--text` can allow grep to parse binary files as text files.

