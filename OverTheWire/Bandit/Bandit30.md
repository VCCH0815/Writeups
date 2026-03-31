# Bandit30

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 31-Mar-2026
**SSH:** ssh bandit30@bandit.labs.overthewire.org -p 2220
**Password:** qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

--- 
```
There is a git repository at `ssh://bandit30-git@bandit.labs.overthewire.org/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
```
Running `git branch -a` revealed a few branches, but did not seem to show anything useful.

Using tab completion, I found a file named `secret` when using `git show`, which revealed the password.

![](attachments/Pasted%20image%2020260331143052.png)
**secret is not a file but a git tag**
# References

