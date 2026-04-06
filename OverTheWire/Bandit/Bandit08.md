# Bandit8

**Platform:** OverTheWire  
**OS:** Linux
**Category:** Unix/Linux Basics
**Date Completed:** 24-Feb-2026 
**SSH:** ssh bandit8@bandit.labs.overthewire.org -p 2220
**Password:** dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

--- 
```
Goal : The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
```
Using `cat data.txt` reveals a bunch of random strings which all may be a password, the goal states that the correct string only occurs once, from the `Commands you may need to solve this level` part of the OverTheWire page, I see a command named uniq which may help me achieve this.

From [Counting with uniq](#Counting_with_uniq), Brian shows how to use sort and uniq how many times a string appears.

```
Let's look at a simple example first to highlight the fundamental concepts. Given a file called fruit with the following contents:

apples
oranges
apples

you can discover how many times each word appears, as follows:

% sort fruit | uniq -c
  1 oranges
  2 apples
  
  What's happening here? First, sort fruit sorts the file. The result ordinarily would go to the standard output (in this case, your terminal), but note the | (pipe) that follows. That pipe directs the output of sort fruit to the input of the next command, uniq -c, which prints each line preceded by the number of times
```

With this knowledge, I apply it on `data.txt`

`sort data.txt | uniq -c`

From the results, I simply select the one with only one occurrence.

![](attachments/Pasted%20image%2020260224143329.png)

# References
#### Counting_with_uniq
https://www.linuxjournal.com/article/7396