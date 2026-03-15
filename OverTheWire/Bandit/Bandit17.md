# Bandit17

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 15-Mar-2026
**SSH:** ssh bandit17@bandit.labs.overthewire.org -p 2220
**Password:** EReVavePLFHtFlFsjn3hyzMlvSuSAcRD

--- 

```
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**
```

From the [grep man page](#Grep_man_page), I found a few options I can use.

```
       -f FILE, --file=FILE
              Obtain patterns from FILE, one per line.  If this option is
              used  multiple  times or is combined with the -e (--regexp)
              option, search for all  patterns  given.   The  empty  file
              contains zero patterns, and therefore matches nothing.

       -v, --invert-match
              Invert the sense of matching, to select non-matching lines.
```

`grep -f passwords.old -v passwords.new

I start by using `-f` to give grep a list of passwords, then use `-v` to indicate I want to find what is not matched.

![](attachments/Pasted%20image%2020260315160710.png)


# References
#### Grep_man_page
https://linuxcommand.org/lc3_man_pages/grep1.html
