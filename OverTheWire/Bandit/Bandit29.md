# Bandit29

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 31-Mar-2026
**SSH:** ssh bandit29@bandit.labs.overthewire.org -p 2220
**Password:** 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

--- 
```
There is a git repository at `ssh://bandit29-git@bandit.labs.overthewire.org/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
```

I start by looking for different branches. `git branch`

There is no other branches.

running `git log` I see two commits, to see the changes, I run `git diff`
![](attachments/Pasted%20image%2020260331141251.png)

Seems like there is nothing important.

When looking at the above, I noticed a origin/dev remote repo, and running `git show origin/dev` revealed the password.

**`git branch` does not show remote branches, use `git branch -a`**
![](attachments/Pasted%20image%2020260331141918.png)
# References

