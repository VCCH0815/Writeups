# Bandit20

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 20-Mar-2026
**SSH:** ssh bandit20@bandit.labs.overthewire.org -p 2220
**Password:** 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

--- 
```
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
```

After reading the goal, my hypothesis is that I should start a netcat listener, connect to it using the binary provided, the send the password of this level back to the binary.

 I start by opening a netcat listener, I run `nc -vlnp 9999`.

![](attachments/Pasted%20image%2020260320115930.png)

On a new command line, I connect back to bandit20, and run `./suconnect 9999`, which is the binary that is provided.

Going back to the netcat listener, I successfully got a connection, I then paste the password of the current level, `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`, which returned the password for bandit21.
![](attachments/Pasted%20image%2020260320120155.png)
# References

