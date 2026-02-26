# Bandit10

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 26-Feb-2026
**SSH:** ssh bandit10@bandit.labs.overthewire.org -p 2220
**Password:** FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

--- 

```
Goal: The password for the next level is stored in the file data.txt, which contains base64 encoded data
```

Using `cat data.txt` revealed the following.
![](attachments/Pasted%20image%2020260226204922.png)

Since I know that this is base64 encoded from the Goal paragraph, I copied and pasted this line to [CyberChef](#CyberChef).

I Simply added the **From Base64** Operation and got the password.

![](attachments/Pasted%20image%2020260226205117.png)

# References
#### CyberChef
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=VkdobElIQmhjM04zYjNKa0lHbHpJR1IwVWpFM00yWmFTMkl3VWxKelJFWlRSM05uTWxKWGJuQk9WbW96Y1ZKeUNnPT0
