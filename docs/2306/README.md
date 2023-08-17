# Learned that `scp://` is a thing (like `ssh://`)

Today I learned that there is a formal URI for `scp` (by reading the man page).

```sh
scp scp://user@localhost:22//home/rwxrob/somefile.txt /tmp/
scp scp://user@localhost:22/somefile.txt /tmp/
```

It is relative by default, which I wasn't expecting to be the case. When I tried `//` for force root I was pleasantly surprised. I think this works for Windows ssh servers as well (but haven't tested).

I've known about the equivalent for ssh for a while:

```sh
ssh ssh://user@localhost:22 tail -1 somefile.txt
```
