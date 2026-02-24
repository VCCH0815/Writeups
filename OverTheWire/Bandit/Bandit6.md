# Bandit 6

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 24-Feb-2026
**SSH:** ssh bandit6@bandit.labs.overthewire.org -p 2220
**Password:** HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

--- 
```
Goal: The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
```

Since the file is stored "Somewhere on the server" I know to use `find /` to search the whole file system.

I chose to filter by files that are size 33 bytes first as that is the easiest. `2>/dev/null` to redirect errors.

`find / -size '33c' 2>/dev/null

The result was alot so I did research on how to filter by user and group properties.

From the [manpage](#Find) of find, I found the following options.

```
-group gname
              File belongs to group gname (numeric group ID allowed).

-user uname
              File is owned by user uname (numeric user ID allowed).
```

With this knowledge, I update my command
` find / -size '33c' -group bandit6 -user bandit7 2>/dev/null 

![](attachments/Pasted%20image%2020260224141408.png)

`cd /var/lib/dpkg/info`

`cat bandit7.password`

# Conclusion
Using the knowledge I learned from [Bandit5](Bandit5.md), I started by filtering from size, but it was not as useful. I then learnt more options for the `find` command such as `-group` and `-user`.
# References
#### Find
https://manpages.ubuntu.com/manpages/noble/man1/find.1.html