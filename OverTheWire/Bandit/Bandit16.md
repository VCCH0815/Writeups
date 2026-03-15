# Bandit16

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 14-Mar-2026
**SSH:** ssh bandit16@bandit.labs.overthewire.org -p 2220
**Password:** kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

--- 
```
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**
```

Reading the goal, this room seems to be a repeat of the previous [Bandit15](Bandit15.md), but now the port is unknown, so I start with a [Nmap](../../../Hacking%20Notes/Random%20Notes/Nmap.md) scan with the range 31000-32000

`nmap -sV 127.0.0.1 -p31000-32000

```
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown
```

now with a few candidates, I try them one by one using the following command.

`openssl s_client -connect 127.0.0.1:31046`

Out of these ports, `31518` and `31790` had a response. I tried putting the current password but both failed with the `KEYUPDATE`. 

Reading the OverTheWire page, it suggests reading the [manpage](#open_ssl) for `KEYUPDATE` errors.

What I found was that `Q,R,k,K` are commands that trigger an action, since the password starts with a lowercase k, I suspect it is interpreting it as a command therefore 'failing'.

Knowing this, I first try to find which port is correct by trying to get the `Wrong Password` error.

I ran openssl s_client -connect 127.0.0.1:[PORT] with both ports and for the password I use the word 'test'.

On the port `31790`, I found the error.
![](attachments/Pasted%20image%2020260314165838.png)

Now with the correct port, I just have to find a way to input the password without triggering `KEYUPDATE`.

I google 'openssl bypass connected commands' to see my options and one of them was to use the flag -quiet.

This seems to work but it returns a RSA private key back, which I assume is used for the next level.

I copy the key to a file `bandit17_rsa` then I run this command on a new command line.

`chmod 400 bandit17_rsa` to change the permissions because an error occurs when the permissions are too open.

Then, `ssh bandit17@bandit.labs.overthewire.org -p 2220 -i bandit17_rsa ` to login to bandit17 using the key.

From [Bandit13](Bandit13.md), I know that the password is located in `/etc/bandit_pass`, so using `cd /etc/bandit_pass`, and `cat bandit17` I get the password for bandit17.
# References
#### open_ssl
https://docs.openssl.org/3.0/man1/openssl-s_client/#connected-commands