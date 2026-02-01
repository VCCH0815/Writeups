Password : 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

The password is stored in a file that has spaces in its filename.

Spaces in filename will be treated as separate arguments.

to overcome this, wrap the filename in quotes.
`
`"File name with spaces"

With this knowledge i tried `cat "--spaces in this filename--` but unfortunately it did not work.

I tried adding a `./` prefix as used at [Bandit1](Bandit1.md) and successfully retrieved the password.

`cat ./"--spaces in this filename--"`
#### References
https://linuxhandbook.com/filename-spaces-linux/