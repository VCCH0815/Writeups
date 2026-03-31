# Bandit31

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 31-Mar-2026
**SSH:** ssh bandit31@bandit.labs.overthewire.org -p 2220
**Password:** fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy

--- 
```
There is a git repository at `ssh://bandit31-git@bandit.labs.overthewire.org/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
```
`README.md` contained the following,
```
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

```
I follow along by creating a file named `key.txt` with the content required. `nano key.txt`

I then add the file to tracking and commit it and push it.

I first run `git add key.txt -f`, I use `-f` because `.txt` files are added to `.gitignore` which have ignore rules.
![](attachments/Pasted%20image%2020260331144624.png)

I then run `git commit`, with a message, and finally `git push`.

![](attachments/Pasted%20image%2020260331144654.png)


# References

