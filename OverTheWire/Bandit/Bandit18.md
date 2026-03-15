# Bandit18

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 15-Mar-2026
**SSH:** ssh bandit18@bandit.labs.overthewire.org -p 2220
**Password:** x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

--- 

```
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
```

Upon logging in over ssh, I get logged out automatically and the connection is closed.

I search for ways to override .bashrc and found that I can run the following command.

`ssh -t username@remote_host 'bash --norc'`

`--norc` will skip all rc files, rendering the `.bashrc` useless.
 ![](attachments/Pasted%20image%2020260315162504.png)
 
# References
#### bash
https://unix.stackexchange.com/questions/55613/run-ssh-login-command-without-modifying-remote-bashrc
