# Use Terminal Color Safely with `[[ -t 1 ]]`

Even though Rob Pike is rumored to have said that color in the terminal
is "juvenile", and even though *not* having color created a production
bug at work just last week from someone who would have caught
`AllowTcpForwarding` is not an `/etc/ssh_config` parameter, still color
is not only fine it is a good tool to help identify context and syntax.
But sometimes, color can really fuck up your output. For example, say
you create a wonderful documentation and usage that is in color. Then
bam, you redirect that to a file and color ruins your day, badly. 

Enter `[[ -t 1 ]]` which tests if the running script has an interactive
`stdout` file descriptor (you could check any). This effectively means,
"Yes, you are interactive and a terminal user is looking at the output."
Now you can turn color on or off and be fine for pipes. If you want to
get fancy you can provide an option to force color like `grep` or `ls`
with `--color=always`. Here's an example:

```bash
declare B=$'\033[1m' X=$'\033[0m'
[[ ! -t 1 ]] && B= && X=
```

That's really it. This makes a great snippet.

    #bash #snippets #tips #linux #color #terminal
