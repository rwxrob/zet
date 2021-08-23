# Google Bash Style Guidelines are Shit

Once upon a time I valued Google's Bash Style Guidelines. Now I think
they are absolute shit. They obfuscate the code with inline
documentations that cannot be used anyplace else at all. The
`template-bash-command` that I created, with embedded CommonMark
Markdown documentation stored in a bash 4+ associative array that can be
rendered as a `README.md` file is objectively superior on every level,
particularly because it can be combined with GitHub to provide
search-ability across all bash commands used.

Plus my `template-bash-command` supports automatic tab completion and a
host of other stuff the Google "guidelines" can't even dream of
implementing. 

Also, can we all just agree that `"${foo}"` (unless you need it)
unnecessarily obfuscates code and makes it harder to read and write.
This is bash we are talking about. It's suppose to be *fast* to
write above all. Scripting in bash is about developer speed, not
long-term maintainability. Sure a lot of bash will be around, but this
stupid constraint for `${}` is just fucked.

Calling out the usage and return values of every function is still a
sound idea, I suppose. But, honestly, if you are writing code well it
will be immediately and totally obvious. If it's not, you're writing the
code wrong. Besides, a rhetorical explanation of what the function does
is *always* better than trying to overengineer every possible option and
return value into a pseudo-textual-database at the beginning of every
function. You can really tell these "guidelines" where created by
engineers (and not technical documentation writers). 

> 🤬
> Hey Google, might want to have a professional technical writer chime
> in on your shitty style guidelines before forcing them on your entire
> company. Google gets so much shit absolutely wrong it's embarrassing.
> I'm still amazed when I hear people talk about "following the Google
> unicorn".

A better alternative to Google style guidelines is just plain and
simple: pass `shellcheck`. I really seriously regret having told
*anyone* to follow those guidelines (especially since one of them went
on to create a ton of code that I now have to sift through and work with
every day).

See also:

* <https://google.github.io/styleguide/shellguide.html>
* <https://github.com/rwxrob/template-bash-command>

Tags:

    #bash #shell #scripting #style #guidelines #google
