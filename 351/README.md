# Don't Use Vim Buffers, They Fail to Meet the Need

Even though `vi` has buffers they inevitably fail you. If you aren't in
`vi` you cannot use them. In `vim` the buffers persist across sessions,
but only if you close out a session and start a new one. If you have
several `vi` sessions, one to a TMUX pane/window, you will see that this
can get in the way.

The solution that most of the world (that doesn't understand the UNIX
philosophy) will suggest is to only use one editing session. But you and
I both know that's just stupid. The entire point of `vi` is to be able
to quickly open and edit a file anywhere, anytime, not force you into
having to navigate to the file from within a `vi` session (which is the
asinine motivation for people putting fuzzy-finder shit into their text
editor when just the UNIX command line would have been way better). This
solution is no solution at all.

There's another problem with this "solution". If you don't have your
`.viminfo` configuration exactly correct it will often truncate your
buffer cut removing all the lines and only preserving a fraction of
them. I've done this. It's disastrous. 

The right way to do this is to keep with the UNIX philosophy and put
everything in a file, no buffers at all. The file *is* the buffer. I use
`!ip tee /tmp/foo` or `!ip w! /tmp/foo` or something like it. You can
just `:r /tmp/foo` from the same file/session or another one without
ever having a problem. I sometimes prefer `tee` because it doesn't whine
about overwriting files like `w` does by default everywhere.

You can easily create a helper filter command to save on a lot of typing
while still not violating the UNIX philosophy or requiring any special
plugins.

In a file called `yyy` in the `PATH`:

```bash
#!/bin/bash
> /tmp/buf
while IFS= read -r line;do
  echo "$line" >> /tmp/buf
  echo "$line"
done
```

If you want a delete use `ddd`:

```bash
#!/bin/bash
> /tmp/buf
while IFS= read -r line;do
  echo "$line" >> /tmp/buf
done
```

And in a file called `ppp`:

```bash
#!/bin/bash
exec cat /tmp/buf
```

Yes, those weird file names. If that bothers you use something else. I
like them because they are similar to what I would use from within `vi`.

You can get a crazy as you want with this. The important thing is that
would you are using can be used *anywhere*, not just within your editor.
So you can combine this with your regular use of the UNIX command line,
in the true UNIX way:

```
tail somefile | yyy
```

Then from within `vi` just use the normal `!!ppp` or just `:r /tmp/buf`.

    #vim #tips #unix #linux
