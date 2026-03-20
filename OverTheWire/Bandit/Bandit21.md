# Bandit21

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 20-Mar-2026 
**SSH:** ssh bandit21@bandit.labs.overthewire.org -p 2220
**Password:** EeoULMCra2q0dSkYj561DX7s1CpBuOBt

--- 
```
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
```
The goal states that there is a cron job running at a regular interval. If the cron job is running at a higher privilege, I may be able to take advantage of it to print out the command for the next level.

I start by going to the directory suggested by the goal. `cd /etc/cron.d`. I see a `cronjob_bandit22`, so I run `cat cronjob_bandit22` to know more.
![](attachments/Pasted%20image%2020260320120605.png)

Seems the file is located at `/usr/bin/cronjob_bandit22.sh`, so I use `cd` to redirect there.

`cd /usr/bin`

`cat cronjob_bandit22.sh `

![](attachments/Pasted%20image%2020260320120759.png)
It looks like the cronjob is writing the contents of `/etc/bandit_pass/bandit22`, which is the password for the next level, to `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

So all I have to do is view the password in this directory.

`cd /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

![](attachments/Pasted%20image%2020260320121051.png)

**t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv is not a folder**
# References

