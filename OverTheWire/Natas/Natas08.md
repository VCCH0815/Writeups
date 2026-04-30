# Natas08

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Web
**Date Completed:** 09-Apr-2026
**Username:** natas4
**Password:** xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q
**URL:** http://natas8.natas.labs.overthewire.org

---
Upon logging in, the following is shown,

![](attachments/Pasted%20image%2020260409173752.png)

Reviewing the source code by clicking `View sourcecode`, 
```
`   <?      
$encodedSecret = "3d3d516343746d4d6d6c315669563362";      function encodeSecret($secret) {       return bin2hex(strrev(base64_encode($secret)));   }      if(array_key_exists("submit", $_POST)) {       if(encodeSecret($_POST['secret']) == $encodedSecret) {       print "Access granted. The password for natas9 is <censored>";       } else {       print "Wrong secret";       }   }`
```
My input is put through the `base64_encode`, `strrev` which I assume is string reverse, and `bin2hex` functions via the `encodeSecret` function.

It is then compare with the value of `$encodedSecret`. 

I just need to reverse engineer the value of `3d3d516343746d4d6d6c315669563362`.

Using the following formula on [CyberChef](#CyberChef), I reverse engineer a secret code that successfully got the password.

![649](attachments/Pasted%20image%2020260409175100.png)
Apparently the ToBinary is not needed. From ChatGPT, it seems that it is because `bin2hex` is from `binary data` to hex, NOT `binary` to hex. `Binary data` and `Binary` are different things.

# References
#### CyberChef
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')To_Binary('Space',0/disabled)Reverse('Character')From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=M2QzZDUxNjM0Mzc0NmQ0ZDZkNmMzMTU2Njk1NjMzNjI