# Natas07

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Web
**Date Completed:** 09-Apr-2026
**Username:** natas7
**Password:** bmg8SvU1LizuWjx3y7xkNERkHxGre0GS
**URL:** http://natas7.natas.labs.overthewire.org

---
After logging in, I am greeted with two tabs.
![](attachments/Pasted%20image%2020260407104624.png)

Using F12 to open inspector revealed a hint, 
` hint: password for webuser natas8 is in /etc/natas_webpass/natas8 `
``


The following is the full URL for natas7
`http://natas7.natas.labs.overthewire.org/index.php?page=home`
I see that the ?page=home section, perhaps I can navigate to `/etc/natas_webpass/natas8` from here.


By trying the URL `http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8`, I get the password for natas8.

![](attachments/Pasted%20image%2020260409173623.png)

# References