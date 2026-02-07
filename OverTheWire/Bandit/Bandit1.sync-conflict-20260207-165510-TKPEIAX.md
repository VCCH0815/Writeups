Password from previous level : ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

Using `ls` revealed a dash.

![](attachments/Pasted%20image%2020251209202711.png)

I didn't know what it was so i googled dashed filename.

Turns out, A dashed filename is difficult to access as they can be interpreted by the command line as an option. 

I tried using `cat -- -` as `--` indicates the end of command options but it does not seem to work.

I tried using the `./` prefix and successfully retrieved the password. [[Bandit1](Bandit1.md)](#^R1)
#### References
https://linux.die.net/abs-guide/special-chars.html ^R1

Filenames beginning with "-" may cause problems when coupled with the "-" redirection operator. A script should check for this and add an appropriate prefix to such filenames, for example ./-FILENAME, $PWD/-FILENAME, or $PATHNAME/-FILENAME.

If the value of a variable begins with a -, this may likewise create problems.

```
var="-n"
echo $var		
Has the effect of "echo -n", and outputs nothing.
```



