# Bandit24

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 25-Mar-2026
**SSH:** ssh bandit24@bandit.labs.overthewire.org -p 2220
**Password:** gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

--- 
```
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time
```
For this level I am expected to brute force a 4 digit pin.

I first run `nc 127.0.0.1 30002` to know what is the daemon

I then use chatgpt to generate a script to brute-force the password

```

prefix="gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"

{
    for ((i=0; i<=9999; i++)); do
        printf "%s %04d\n" "$prefix" "$i"
    done
} | nc 127.0.0.1 30002

```

I give the script permissions `chmod 777 script.sh`, then run it `./script.sh`.

![](attachments/Pasted%20image%2020260325222725.png)
# References

