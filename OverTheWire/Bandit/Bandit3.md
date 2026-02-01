Password : MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

Using `ls` there is a directory named `inhere`. After using `cd` to access it and `ls` to list all files, there was not anything listed out. 

I suspected that there may be hidden files so I used the command `ls -la` to list all files.

Output:
![](attachments/Pasted%20image%2020260130144131.png)

There is a file named `...Hiding-From-You` . Then I simply used `cat` to list it out. 

Seems like `...` will hide a file from a normal `ls`.

A quick google search shows that adding a `.` before a filename will make the system treat it as a system configuration file which is hidden by default.

This shows that I should only use `ls -la` from now on.

