# Natas04

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Web
**Date Completed:** 06-Apr-2026
**Username:** natas4
**Password:** QryZXc2e0zahULdHrtHxzyYkj59kUxLQ
**URL:** http://natas4.natas.labs.overthewire.org

---
Upon logging in, the following message appears.


![](attachments/Pasted%20image%2020260406154728.png)

Seems like I need to spoof something somewhere.

After capturing a request with burpsuite, I alter the Referer Request header from `http://natas4.natas.labs.overthewire.org/index.php` to `http://natas5.natas.labs.overthewire.org/`.

![](attachments/Pasted%20image%2020260406161137.png)

![](attachments/Pasted%20image%2020260406161313.png)
# References