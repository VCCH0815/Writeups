Password : 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

`ls -la` shows a directory named `inhere`

In the directory is the following:
![](attachments/Pasted%20image%2020260130145935.png)

I tried using `cat` :
`cat -file04` 
but an error pops up

```
cat: invalid option -- 'f'
Try 'cat --help' for more information.
```

Seems like the - in the filename is being treated as an options prefix.

So I tried previous methods from [Bandit1](Bandit1.md) and [Bandit2](Bandit2.md). 

![](attachments/Pasted%20image%2020260130151326.png)
Seems like all combinations of methods do not work.

Seems like the dash is being interpreted as an option.

According to [Stack Overflow](#^1), A user pointed out that I can use -- to indicate that it is the end of the options.

`cat -- -file00` 

The command above returns the following,
![](attachments/Pasted%20image%2020260205214325.png)
Seems to be working but the output is weird. OverTheWire stated that this is stored in the human-readable file, so I did some research on this.

Using `file -- -file00`, showed what type of file it is.
![](attachments/Pasted%20image%2020260205214624.png)

So, I tried to cat all the files to see what I can get. 

`cat -- -file00 -file01 -file02 -file03 -file04 -file05 -file06 -file07 -file08 -file09`

There were some random symbols but the bottom part contained the password. 
![](attachments/Pasted%20image%2020260205215542.png)

It seemed like I didn't approach it correctly so I searched how other people completed it.

I should not have had to cat all the files but instead use the `file filename` command to see which file has the password, which should look like this.

![](attachments/Pasted%20image%2020260205215719.png)

Then I should proceed to cat the file. 

![](attachments/Pasted%20image%2020260205215741.png)


https://stackoverflow.com/questions/5677558/how-do-i-deal-with-a-filename-that-starts-with-the-hyphen-character] ^1