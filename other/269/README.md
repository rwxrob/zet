# Infrastructure Language Programming Needs

First are the *mandatory* languages:

```
POSIX sh -> Bash -> Python -> Go
```

You cannot call yourself an "infrastructure" anything without knowing
how to code in these languages. Literally *everything* is written in one
of them else days.

The first pick after these is Perl for its obvious value for regular
expressions, one-liners, and maintaining the billions of lines of Perl
in the enterprise that have accrued over the last two decades. (I'm
working with thousands of lines right now.) For all intents and
purposes, Perl is just a better Bash and should only be used that way.

```
POSIX sh -> Bash / Perl -> Python -> Go
```

A good infrastructure engineer will likely want to expand and understand
the underlying system calls and perhaps even debug crashes or write or
understand simple device drivers. C is the obvious pick for that.

```
POSIX sh -> Bash / Perl -> Python -> Go -> C
```

To get even further into the hardware side, learning Assembly for a
given chipset is daunting, but fulfilling (and I so want to eventually
learn it myself).

```
POSIX sh -> Bash / Perl -> Python -> Go -> C -> Assembly
```

At that point any other language is just for understanding and likely
not something you would ever need in the day-to-day grind.

Anyone in the tech industry will expect you to have at least a minimum
amount of HTML, CSS, and Vanilla JavaScript, but I'm not adding it to
the list, because they really are an entirely different thing unrelated
to the core infrastructure languages. Node and typescript fall into that
mix as well. They are solidly in the applications space, not the
infrastructure space.

Ruby, however, does have a lot of stuff left in security space. It
straddles application and operations in some organizations, but it is
neither good for infrastructure (dominated by Shell, Python, Go, and C),
nor good for applications (dominated by Typescript, C++, C#, Java).

Crystal is a beautiful Ruby replacement. But it also doesn't know what
it wants to be and has less than zero footprint anywhere significant.
It's a fun, beautiful, toy (like so many).

Speaking of useless toy languages. Rust also doesn't know what the fuck
it wants to be. But worse than that. It fucking *lies* to you about
security and safety fraudulently getting people less able to assess the
language in realistic ways to fall victim to it's trendy,
politically-motivated cult mentality. It's a useless, ugly, trending
language that is as popular as CoffeeScript once was and will likely
share the same fate. No one *serious* is taking Rust seriously and there
are virtual zero jobs in it after being around for longer than Go (and
there are thousands of unfilled Go jobs). Most of Rust's supporters
and board members are from the NodeJS world. I rest my case. If and
when it makes a splash it will be used in WASM (web application space)
and in the embedded and applications spaces that are currently fucking
dominated by C and C++ (with no substantial movement at all in that
space toward Rust). I was talking to my embedded friends and they just
laugh their asses off at Rust when I mention it. They code C all day,
every day. People who waste time learning Rust instead of C absolutely
baffle me.
