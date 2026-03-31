# Bandit27

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 30-Mar-2026 
**SSH:** ssh bandit27@bandit.labs.overthewire.org -p 2220
**Password:** upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB

--- 
```
There is a git repository at `ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.
```

On my local machine with git installed, I run `git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo`.[Reference](#Git_Clone) 

Inside the cloned directory, is a README file with the password for bandit28.
# References

#### Git_Clone
https://stackoverflow.com/questions/5767850/git-on-custom-ssh-port