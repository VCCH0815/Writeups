# Bandit15

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 14-Mar-2026
**SSH:** ssh bandit15@bandit.labs.overthewire.org -p 2220
**Password:** 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

--- 

```
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**
```
Using the knowledge of the previous room, [Bandit14](Bandit14.md), I try `telnet 127.0.0.1 30001`, with the password, `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`, but it failed.

From the goal, it seems like I have to somehow connect over SSL/TLS.

I start with a nmap scan, `nmap 127.0.0.1` but nothing of interest came up.

---
I search for `telnet over ssl tls `, which returned to me a [superuser](#superuser) page. In this page, a user showed a way to use OpenSSL to pipe to TLS connections.


`openssl s_client -connect imap.gmail.com:993`

With this knowledge, I try `openssl s_client -connect 127.0.0.1:30001`, ignoring all the output, typing the password of the current level, `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`, revealed the password for the next level.

![](attachments/Pasted%20image%2020260314162921.png)

# Conclusion
I learned that I can 'pipe' non ssl/tls connections to communicate over ssl/tls.

# References
#### superuser
https://superuser.com/questions/346958/can-the-telnet-or-netcat-clients-communicate-over-ssl