# Bandit28

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 31-Mar-2026
**SSH:** ssh bandit28@bandit.labs.overthewire.org -p 2220
**Password:** Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN

--- 
```
There is a git repository at `ssh://bandit28-git@bandit.labs.overthewire.org/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
```
For this level, I repeat the process for [[Bandit27](Bandit27.md)]. 

I start by cloning the repository.

`git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo

Inside the README file was the following:
```
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx


```

Since the password is not here, I assumed that it may be in another branch or maybe it was edited out, so I check for clues.

Running `git branch`, I found that there wasn't another branch.

Running `git log master` I found commits where the password might have been leaked.[Reference](#Git)
![](attachments/Pasted%20image%2020260331135832.png)

To see the difference between the last commit and the present one, I run `git diff b5ed4b5 8b7c651` and got the password.

![](attachments/Pasted%20image%2020260331140923.png)
# References
#### Git
https://git-scm.com/cheat-sheet