# Bandit32

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 31-Mar-2026
**SSH:** ssh bandit32@bandit.labs.overthewire.org -p 2220
**Password:** 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K

--- 
```
After all this `git` stuff, it’s time for another escape. Good luck!
```

Upon logging in, I am greeted by UPPERCASE SHELL, commands seem to not work.
![](attachments/Pasted%20image%2020260331144916.png)
I start by going through the recommended commands, `sh` and `man`.

It seems like my commands are being translate to uppercase which results in an error.

On the [sh man page](#sh), I found some symbol commands that can be used.
```
## Reserved Words

_Reserved words_ are words that have a special meaning to the shell. The following words are recognized as reserved when unquoted and either the first word of a simple command (see **SHELL GRAMMAR** below) or the third word of a **case** or **for** command:

**! case do done elif else esac fi for function if in select then until while { } time [[ ]]**
```
My theory is that since normal words become uppercase, therefore making them denied, there could be a "symbol command" I can use to escape the shell.

Sure enough, I found the following,
```
**0**

Expands to the name of the shell or shell script. This is set at shell initialization. If **bash** is invoked with a file of commands, **$0** is set to the name of that file. If **bash** is started with the **-c** option, then **$0** is set to the first argument after the string to be executed, if one is present. Otherwise, it is set to the file name used to invoke **bash**, as given by argument zero.
```
Running `$0` gave me a usable shell.
![](attachments/Pasted%20image%2020260331223653.png)

Running `cat /etc/bandit_pass/bandit33` reveals the password.
# References

#### sh
https://linux.die.net/man/1/sh
