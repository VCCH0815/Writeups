# Bandit25

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 26-Mar-2026
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

## Attempt 1
Looking this up on [google](#SSH), I found a few keywords I could search around what is happening. `nologin configuration` and `default shell`. I start with default shell because the goal said something about the shell not being /bin/bash.

Cheking bandit25's shell, it is /bin/bash, so maybe it was not for bandit26, so I searched for ways to change it and came across a command [`chsh`](# chsh).

`sudo -u bandit26 chsh -s /bin/bash`

but I do not have sudo privileges.

## Attempt 2
I go back to bandit25 and first start by finding what shell bandit26 is running.

Using google, I found a command I could use.

```
grep "^$USER" /etc/passwd
```
Using this command I found that bandit26 is running `/bin/showtext`

![](attachments/Pasted%20image%2020260326170206.png)

Going to `/usr/bin` and running `cat showtext` I found the following script.

![](attachments/Pasted%20image%2020260326170700.png)

Since showtext is specified as the shell for bandit26, the script runs on login.

Searching Google on how to ignore scripts on SSH login, I found the following commands.

`ssh user@hostname /bin/dash`

`ssh user@hostname "bash --noprofile --norc"'

But both of these commands do not work

## Attempt 3
I start by reading the man pages of the commands recommended.

On the more man page, I found something unusual

```
ENVIRONMENT         [top](https://man7.org/linux/man-pages/man1/more.1.html#top_of_page)

       The **more** command respects the following environment variables, if
       they exist:

       **MORE**
           This variable may be set with favored options to **more**.

       **SHELL**
           Current shell in use (normally set by the shell at login
           time).

       **TERM**
           The terminal type used by **more** to get the terminal
           characteristics necessary to manipulate the screen.

       **VISUAL**
           The editor the user prefers. Invoked when command key _v_ is
           pressed.

       **EDITOR**
           The editor of choice when **VISUAL** is not specified.
```

The environment TERM is also used in the script for `showtext`.

**Got stuck here**

## Solution
Since the script runs the `more` command, by resizing the display of the terminal, you can force the more command to output line by line, stopping it from executing `exit`.
```
**more** is a filter for paging through text one screenful at a time.
```

Then typing `v` will open a vi window, then to retrieve the password, use `:e /etc/bandit_pass/bandit26` to open the file containing the password.

Then, to get a real shell, run `:set shell=/bin/bash` and then `:sh`.
# References
#### SSH
https://stackoverflow.com/questions/61785078/ssh-closes-connection-immediately-after-successful-login-for-a-specific-user

#### chsh
https://stackoverflow.com/questions/13046192/how-to-change-the-default-shell-in-linux

https://askubuntu.com/questions/28969/how-do-you-change-the-default-shell-for-all-users-to-bash

