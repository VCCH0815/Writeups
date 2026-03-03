# Bandit13

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 03-Mar-2026
**SSH:** ssh bandit13@bandit.labs.overthewire.org -p 2220
**Password:** FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

--- 

```
Goal: The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.
```

For this level I am given a private key, to access bandit14 to retrieve the password there.

To login using a key, I first copy the key to my own system and give it a name id_rsa. To be able to use this key, I need to run `chmod 400 id_rsa` to change its permissions.

I then run `ssh -i id_rsa bandit14@bandit.labs.overthewire.org -p 2220` to access bandit14 and retrieve the password.

![](attachments/Pasted%20image%2020260303184017.png)




# Conclusion
I learnt how to SSH with a rsa key, and also the key will be rejected if the permissions are too open.
# References
#### SSH
https://unix.stackexchange.com/questions/23291/how-to-ssh-to-remote-server-using-a-private-key