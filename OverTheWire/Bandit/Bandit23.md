# Bandit23

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 22-Mar-2026
**SSH:** ssh bandit23@bandit.labs.overthewire.org -p 2220
**Password:** 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

--- 
```
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
```

I start by going to `/etc/cron.d` to view the cronjob. `cd /etc/cron.d`

Viewing `cronjob_bandit24` revealed `/usr/bin/cronjob_bandit24.sh`

```
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
```

At `/usr/bin`, I run ` cat cronjob_bandit24.sh`

```
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

```

## Attempt 1
I should create a shell script that copies the password from `/etc/bandit_pass`, which should be bandit24, since the script is run as bandit24 which the owner is not bandit23 as I see a timeout. The script should be placed in `/var/spool/bandit24/foo`

`cat /etc/bandit_pass/$myname > /tmp/$mytarget`

I start by creating my script file
```
#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/zxcvbnm123

```

then copying it over to `/var/spool/bandit24/foo`.

`nano zxcvbnm123.sh`

Running `file zxcvbnm123.sh` does reveal that my file is there.

Putting the script to chatgpt, it seems that the code block,
```
if [ "${owner}" = "bandit23" ]; then  
timeout -s 9 60 ./$i  
fi
```
Means that it will execute the file if the owner is bandit23, which is who I currently am. So I do not need to make changes to ownership of the script I use.

I however, need to give it execute permissions.

```
chmod 777 zxccvbnm123.sh
```

I start by making my own folder in  `/tmp`. `mktemp -d`, in the folder, I recreate the script then give it permissions.

Finally I move it to `/var/spool/bandit24/foo`.

`mv zxcvbnm123.sh /var/spool/bandit24/foo`

After giving some time for the script to run, I get the password.
`cat /tmp/zxcvbnm123`
# References

