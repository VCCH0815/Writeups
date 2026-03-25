# Bandit22

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 22-Mar-2026 
**SSH:** ssh bandit22@bandit.labs.overthewire.org -p 2220
**Password:** tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

--- 
```
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

```
I start by `cd`ing to `/etc/cron.d`, then running `cat cronjob_bandit23` to view the cronjob.

`@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
`* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null`

I `cd` to `/usr/bin`, then `cat cronjob_bandit23.sh` to view the script.
```
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget

```

Reading this script, it seems like I need to 'decode' the value of $mytarget. From the script, it first sets the variable of `myname` as the output of `whoami`, then sets `mytarget` to the output of `echo I am user $myname | md5sum | cut -d ' ' -f 1`. So, if I want to get the password of `bandit23`, I should run the same command, with the value of `myname` being `bandit23`, with the commands provided to get the value of `mytarget`.

`echo I am user bandit23 | md5sum | cut -d ' ' -f 1`
The above command will get the value of `mytarget`, `8ca319486bfbbc3663ea0fbe81326349`
, which I can then run `cat /tmp/8ca319486bfbbc3663ea0fbe81326349`. 



![](attachments/Pasted%20image%2020260322201542.png)
# References

