# Shell Scripting is Just So Much Faster

I've always put priority on getting shit done fast and there is simply
nothing faster than shell scripting, even POSIX. With `set -e` to
automatically error on any failure all the error handling is essentially
taken care of for you. I really have a hard time justifying the crazy
extra amount of time to do anything with a more laborious language. Even
Python is a pain in the ass in comparison. Even complicated API web
requests work fine with `curl` and `jq`. I run into people all the time
who start out simple projects in C++, Rust, Go or some language that
keeps them from getting anything actually working. I just don't
understand why. Half the time people throw out most of what they code,
why not rapidly prototype the whole fucking thing in shell, use it for a
while (like a month) and then consider if the thing is worth porting to
another language at all. Perhaps one or two elements of it need to be
written in C or something. *This* is the UNIX philosophy that
practically no one fucking even knows about. Do one thing well, and make
sure it integrates well.
