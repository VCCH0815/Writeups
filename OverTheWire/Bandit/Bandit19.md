# Bandit19

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 20-Mar-2026
**SSH:** ssh bandit19@bandit.labs.overthewire.org -p 2220
**Password:** cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

--- 
```
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
```

From the goal, it suggests that I have to use something about SUID to exploit. SUID allows a user to execute a program with the permissions of the file owner which sometimes is root. To search for this, I run the following:

`find / -type f -perm -04000 -ls 2>/dev/null`

This command finds for programs in `/` with the SUID bit set, `2>/dev/null` redirects errors.

In the results,

`   576663     16 -rwsr-x---   1 bandit20   bandit19      14884 Oct 14 09:26 /home/bandit19/bandit20-do`

![](attachments/Pasted%20image%2020260320114307.png)

Seems like this executable can be used for something.

From the goal, it suggests executing it without arguments to find out how to use it. I run `./bandit20-do`.

![](attachments/Pasted%20image%2020260320114427.png)

Running `./bandit20-do whoami`, revealed that I can run this as `bandit20`.

![](attachments/Pasted%20image%2020260320114509.png)

From the goal, I know the password is stored in /etc/bandit_pass so I run `./bandit20-do cat /etc/bandit_pass/bandit20

![](attachments/Pasted%20image%2020260320114754.png)
# References

