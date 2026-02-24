Password : 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

For this level, the password seems to be hidden in one of the folder, in one of the files.
![](attachments/Pasted%20image%2020260205221022.png)

Some tips were given

```
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
```

So I will need to utilize the find command to filter for these files.

According to [this](#Find_Command) article,
```
The -size option requires a "+/-n[UNIT]" parameter to do the search.

The "+" stands for greater than, while the "-" means less than. The --size  option supports six units:

b: 512-byte blocks  
c: bytes  
w: two-byte words  
k: kilobytes  
M: megabytes  
G: gigabytes
```

To filter for files that are 1033 bytes, I can do the following,

`find . -size '1033c'

`.` to specify find to the current directory

![](attachments/Pasted%20image%2020260211221611.png)

using `cd /maybehere07` and `cat .file 2` reveals the password.

![](attachments/Pasted%20image%2020260211221759.png)
# References
#### Find_Command
https://dev.to/baeldung/three-simple-examples-of-the-find-command-3g66

