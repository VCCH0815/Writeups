# Bandit11

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 26-Feb-2026
**SSH:** ssh bandit11@bandit.labs.overthewire.org -p 2220
**Password:** dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

--- 

```
Goal: The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
```

For this level, the page recommends `Rot13` reading material. So I assume Rot13 is used to encode this.

Going to [CyberChef](#CyberChef), I used the `Rot13` operation and got the password.

![](attachments/Pasted%20image%2020260226205654.png)

# References
#### CyberChef
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=VkdobElIQmhjM04zYjNKa0lHbHpJR1IwVWpFM00yWmFTMkl3VWxKelJFWlRSM05uTWxKWGJuQk9WbW96Y1ZKeUNnPT0
