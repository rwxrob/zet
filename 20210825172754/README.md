# Power of the Bash Null Command (:)

You might have been coding in bash for a while and never heard of the
*null command*. Here's the excerpt from the man page (which you can
isolate with `help :` instead):

    :
      Null command.

      No effect; the command does nothing.

      Exit Status:
      Always succeeds.

First time reading you might wonder why you would ever use it. Then you
see things like this:


```bash
: "${EDITOR:=vi}"
```

In fact, that is the only way I have ever seen it used in the wild.
Because the `:=` parameter expansion not only returns the alternate
value (`vi`) but also *assigns it* to the empty variable (`EDITOR`) so you
don't need the extra redundant assignment. You'll see stuff like this
from lesser bash coders all over the Internet (including me before
July 2021):

```bash
[[ -z "$EDITOR" ]] && EDITOR=vi
EDITOR=${EDITOR:-vi}
```

I used to think I was clever with the short-circuit operator assignment,
then even *more* clever when I finally started to grok the power of bash
parameter expansion. Then, I realized the difference between `:-` and
`:=` and suddenly I was asking, "How can I just have a variable
parameter expansion without having to assign it to anything?" Then, and
only then, did I fully understand the true value of "the null command"
(`:`).

Guess what? You can even combine them if they are short enough:

```bash
: "${EDITOR:=vi} ${PAGER:=more}"
```

> ⚠️
> Don't forget to wrap everything in double quotes. If you are using
> `shellcheck` (and you are using `shellcheck`, right?) then you will
> see why. The right side of the null command (`:`) has expansion
> applied to it making it dangerous if you don't.

The null command can also be used where having an empty block of bash
code would otherwise cause an error:

```bash
foo() {
  # boom, not even a comment saves you
}
```

```
.../foo: line 5: syntax error near unexpected token `}'
.../foo: line 5: `}'
```

But replace the comment with a null command and you are golden:

```bash
foo() {
  : # TODO implement me
}
```

The same holds true for `if` and `while` and `for` (but not `case`):

```bash
if [[ true ]]; then
  # boom
fi
```

```
.../foo: line 5: syntax error near unexpected token `fi'
.../foo: line 5: `fi'
```

But adding this humble little colon and it works:

```bash
if [[ true ]]; then
  : # boom
fi
```

Tags:

    #bash #scripting #commands #null #colon #100daysofcode
