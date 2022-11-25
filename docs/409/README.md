# No Need for `vim` Visual Mode

I've been using `vi` and `vim` for over 20 years at this point and not
once have I ever needed "visual mode" (a term that confuses people
because `vi` literally standards for "visual mode" of `ex`). And now
that I am *finally* starting to use `vim`'s `ip` and `ap` stuff (and the
like) I don't need visual mode even more.

The secret is no secret, use `vi` as God intended, with shell
integration. Instead of using visual mode to comment things use `s,^,#
,` and the like. And if that is too much, write a couple `cmt` and
`ucmt` scripts like these and use them with `!{` (in `vi`) and `!ip` in
`vim` which send the current paragraph to the filter scripts you have
created.

Here's `cmt`:

```sh
#!/bin/sh
IFS=
while read -r line; do 
  echo "${1-#} $line"
done
```

And here's `ucmt`:

```sh
#!/bin/sh

while read -r line; do 
  echo "${line#* }"
done
```

These scripts can be used to all sorts of things besides just commenting
and uncommenting. You can also repeat them with dot (`.`) to dedent a
section quickly by one space at a time (but `<ip` and `>ip` do that in
`vim` so only valuable if you only have `vi`).
