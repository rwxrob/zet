# Use Assignment to Clone in Go

Beware of the following code. It doesn't do what you think:

```go
    clones[cloning] = &(*cloning)
```

Your references won't change.

```
2022/03/17 21:46:17 self:  0xc0000661e0 parent: 0x0
2022/03/17 21:46:17 left:  0x0 right:  0x0
2022/03/17 21:46:17 first: 0xc000066230 last:   0xc000066230
2022/03/17 21:46:17
2022/03/17 21:46:17 self:  0xc0000661e0 parent: 0x0
2022/03/17 21:46:17 left:  0x0 right:  0x0
2022/03/17 21:46:17 first: 0xc000066230 last:   0xc000066230
-
```

I believe this is because the compiler optimizes away your cleverness as
being unnecessary redundancy.

To get what you probably want (a clone) you need to use and explicit
assignment to force it to create a copy before taking a reference to
that copy:

```go
    c := *cloning
    clones[cloning] = &c
```

This looks better:

```
2022/03/17 21:40:14 self:  0xc0000661e0 parent: 0x0
2022/03/17 21:40:14 left:  0x0 right:  0x0
2022/03/17 21:40:14 first: 0xc000066230 last:   0xc000066230
2022/03/17 21:40:14
2022/03/17 21:40:14 self:  0xc000066280 parent: 0x0
2022/03/17 21:40:14 left:  0x0 right:  0x0
2022/03/17 21:40:14 first: 0xc0000662d0 last:   0xc0000662d0
```

By the way, to print references use `fmt/log.Printf("%p",ref)`.

I've known about this for a while, but never actually wrote it anywhere.
Best to get the word out.

    #golang #coding #tips #cloning
