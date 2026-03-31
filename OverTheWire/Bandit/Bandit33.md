# Bandit33

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 31-Mar-2026
**SSH:** ssh bandit33@bandit.labs.overthewire.org -p 2220
**Password:** tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0

--- 
```
Congratulations on solving the last level of this game!

At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.

If you have an idea for an awesome new level, please let us know!

```
Looking back at this journey, I am grateful to the OverTheWire team for hosting this resource and learning platform for free. The amount of knowledge I learnt far outweighs what is taught in an education syllabus. 

I started off by getting a grasp of linux in general. At first, learning a new operating system was daunting, but now, I can say that I am confident in using it. I learnt about files in ways I could never think of, from hidden files, to weird file names and even very essential commands I still use today. `ls -la`, `cat`, `file` `grep` and many more.

The second segment refreshed my knowledge on the topic of encoding. I took advantage of tools like CyberChef, gunzip, tar and many more which I know will be a great asset in the future.


The next chunk was starting to get harder for me, requiring me to learn how to ssh with a RSA key, and also figuring out how to connect to localhost using netcat to communicate with daemons hosted. I also was taught to use nmap to scan ports for potential vulnerabilities.

The next important segment I value is the cronjob rooms, from previous studying, I know that cronjobs are a very important area that can be leveraged, but I did not have any notable experience in this. The segments provided exposed me to cronjobs and most importantly requiring me to write my own scripts, which I always forget to `chmod` it with execute privileges.

The "easiest" segment was the git segment, however, it was only easy because it is overshadowed by the harder rooms that require breaking out of shells... Ahem... [[bandit25]].......Ahem. This segment in my opinion is "lacking", but not in the sense of difficulty or depth. The rooms slowly introduced my to git, which I had trouble understanding and admittedly still do, until now. I wished there were more on this topic of git, but I know it is difficult to implement "vulnerabilities" in a sense for public and over ssh. Perhaps what I need is just real life experience in working with git.

The final type of room and what was the hardest but most fun was shell escape rooms. These rooms tested my patience in going through man pages line by line, looking for that extra function a developer decided to implement and using it to bypass a "broken shell". Looking back it seems there were fewer rooms of this type than I thought, meaning I spent a lot of time figuring it out. [[Bandit25]] was the most notable room as it had the most intricate solution that I could never have had figured out on my own. This room an example of needing to really read everything that the program have to offer.

The only complaint I have would be the lack of "small tips" to just nudge me in the right direction.

All in all, Bandit really pushed me to my limits and became a stepping stone to my journey as a Pentester. I will definitely be attempting all the other rooms that they provide.

Thank you OverTheWire team!

# References

