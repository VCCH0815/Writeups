# Natas06

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Web
**Date Completed:** 07-Apr-2026
**Username:** natas6
**Password:** 0RoJwHdSKWFTYR5WuiAewauSuNaBXned
**URL:** http://natas6.natas.labs.overthewire.org

---
Logging in to natas6 revealed a form that requires me to submit a secret. The view sourcecode button revealed that the password is stored at `includes/secret.inc`.

![](attachments/Pasted%20image%2020260407102927.png)

Navigating to `http://natas6.natas.labs.overthewire.org/includes/secret.inc` and opening the inspector with F12 revealed the secret, which I then input to the form to get the password.
![](attachments/Pasted%20image%2020260407103011.png)
# References