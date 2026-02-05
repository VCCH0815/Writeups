```
Username: natas2
Password: TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI 
URL:      http://natas2.natas.labs.overthewire.org
```


![](attachments/Pasted%20image%2020260204174757.png)The page source seems to contain an `<img>` tag, so the first thing I attempted was to delete it in hopes of revealing something but nothing came out. 

The clue there is nothing on this page may indicate that there is another page.

Since the image is in a directory, `files/pixel.png` I tried to access the directory.

`http://natas2.natas.labs.overthewire.org/files/`

Sure enough there was a file named `users.txt`.

![](attachments/Pasted%20image%2020260204175143.png)

Accessing the `users.txt` file revealed the password. 
![](attachments/Pasted%20image%2020260204175214.png)