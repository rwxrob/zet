# No Globbing in Bonzai, Just Functional Pipes

I love globbing on the shell. I have `**/*` active in bash and have used
it a lot. But globbing has always been fundamentally a bad idea. It's
limited, imprecise, and frankly unsafe because often it fails in ways
that you would never know. For example, if you use more arguments than
are allowed on the shell. It just silently truncates your list. That's
fucking horrible.

So what are the alternatives?

While loops `while IFS= read -r` is the only truly safe way to do it.
And no one ever remembers the IFS nor the -r (and frankly it's hard to
remember why). Python users look at that and wonder what the fuck is
going on. Rather than get into that, I just want to note the status quo
and how broken it is so we can consider a sane alternative in
BonzaiShell.

The good part of that `while` loop is that it is taking in input. But
god help you if you `cat file | while` and mask all your variables. That
is one of the biggest shell scripting fails in history. You *must* use
`while < file` or your script will fail in disastrously obscure ways.
It's these kind of esoteric exceptions that make people just hate coding
in shell (any of them). We need to avoid all that.

Piping into a loop, or an `each` command is really the way to go.

```
z produce output with lines -- each line foo the line -- each line
prefix someprefix
```

We will make it so the `z shell` command just starts a REPL. But with a
pipe operator we can connect output to the input of the next line:

```
produce output with lines
--
each line
  foo the line
--
prefix someprefix
```

> 😊 It makes me absolutely giddy that all that code could be easily
spoken into a phone without even touching the keyboard.

That just makes me realize that one or more spaces at the beginning of a
new line is all we need to make sure it goes with the previous line ---
especially since we will absolutely have to observe single quotes for
long strings. This means that seeing *any* dashes, that are not within
quotes, means you have a connection between them.

It's the most functional and "unix"-ey. And Bonzai easily accommodates
any number of commands that double as operators. It is one of the
pristinely beautiful things about approach the entire user interface
using a *truly* functional paradigm. There is no BonzaiShell "language"
because there never needs to be. This is why "everything turns out Lisp"
because it's the same idea. Just connect the outputs from one command to
the next. That's Bonzai.

But we need an operator that won't rock the boat. It could be any word,
but words are too often arguments to other things. It could be all upper
case, but that is too hard to speak into a voice interface.

* Double dash (`--`) works and is easily spoken into any phone.
* Right arrow emoji (➡) is also speakable but hard to see.
* The plus (➕) is really easy to read every but doesn't denote piping.
* The arrow ligature (`-->`) is interpreted as an output redirect.

Double dashes just make the most sense.

    #bonzai #design #pipes #globbing #shell
