```
Username: natas3
Password: 3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
URL:      http://natas3.natas.labs.overthewire.org
```

![](../../../Hacking%20Notes/attachments/Pasted%20image%2020260204175606.png)

When viewing the page source, I found the following comment:
` No more information leaks!! Not even Google will find it this time... `
This means that there is some information in the robots.txt file, which is used to tell Google what files that the owner does not want to share with their search engine.


![](attachments/Pasted%20image%2020260205212232.png)
Sure enough, appending the `/robots.txt` to the end of the URL showed a hidden directory `/s3cr3t/`

![](attachments/Pasted%20image%2020260205212328.png)
Appending `/s3cr3t/` to the end of the URL revealed the users.txt, which contained the password for the next level.
