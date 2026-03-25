# Bandit25

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** YYYY-MM-DD 
**SSH:** ssh bandit25@bandit.labs.overthewire.org -p 2220
**Password:** iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

--- 
```
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

> NOTE: if you’re a Windows user and typically use Powershell to `ssh` into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.
```

running `ls` I see a ssh key for bandit26, which should be for the login.

I first download the sshkey file to my local machine

`scp -P 2220 bandit25@bandit.labs.overthewire.org:/home/bandit25/bandit26.sshkey /home/kali/Downloads`

Then connecting to bandit26 using the key.

`ssh -i /home/kali/Downloads/bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220`

Upon logging in, the connection is immediately closed.

# References

