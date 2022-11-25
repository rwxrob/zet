# Read Interactive Input from User to `stderr`

📺 <https://youtu.be/Q2fm7lzALO8>

Often when looping over input (from `stdin`) you might want to prompt
the user for input but you no longer can use `stdin` for that because it
is in use. Consider the following (broken) example:

```bash
#!/usr/bin/bash
while IFS= read -r line; do
  read -p "Echo '$line'? " resp
  [[ $resp =~ ^[yY] ]] || continue
  echo "$line"
done < <(ls)
```

The code above does *not* wait to prompt you. Instead, it reads the
prompt immediately from the next line of `stdin` (another `ls` line).
That's probably not what you were expecting.

The fix (thanks to the Internet) is to tell `read` that you want to read
*input* from `stderr` instead of `stdin`: 

```bash
  read -u 2 -p "Echo '$line'? " resp
```

That's probably the most counter-intuitive thing you have heard all day
and it's the reason people don't trust bash for production software, and
they shouldn't (but neither should you trust any loose scripting
language including Python, Perl, and JavaScript). Those eccentricities
might be permissible for personal and prototype projects, but you want
to avoid that kind of magic at all costs in production software (which
is where a beautifully unsexy, strongly typed, battle-hardened language
like Golang comes in).

