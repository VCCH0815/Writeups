# Bandit14

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 14-Mar-2026
**SSH:** ssh bandit14@bandit.labs.overthewire.org -p 2220
**Password:** MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

--- 

```
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
```

I know that the IP address for localhost is 127.0.0.1, but I do not know how to *submit* it.

Looking at the OverTheWire site, it suggests a few commands which I think might be useful, one that sparked was `nmap`, so I did an Nmap scan.

`nmap 127.0.0.1`

```
  STATE SERVICE
22/tcp    open  ssh
1111/tcp  open  lmsocialserver
1840/tcp  open  netopia-vo2
4321/tcp  open  rwhois
8000/tcp  open  http-alt
30000/tcp open  ndmps
50001/tcp open  unknown

```

Seems like there is something on port 30000.

A quick google on ndmps on port 30000 revealed that it's full name is Network Data Management Protocol Secure.

However I did not know what to do with this information.

I go back to trying suggested commands, starting with telnet.

According to the man pages, I can run `telnet 127.0.0.1 30000`. 

```
bandit14@bandit:~$ telnet 127.0.0.1 30000
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
?/help
Wrong! Please enter the correct current password.
Connection closed by foreign host.
```
I try `?/help` to get some commands I can use, but seems like it is looking for a password. From the goal, it says to submit the current password so I try submitting the current password of bandit14 `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`, successfully retrieving the password for the next level.

![](attachments/Pasted%20image%2020260314161651.png)

# Conclusion

# References