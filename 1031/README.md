# Set `PATH` to Nothing to Distinguish Builtins

I was reminiscing earlier about how in the old days we would never do
things like `#!/usr/bin/env bash` because of how insecure it is. Another
thing we would do is set `PATH` explicitly to make sure nothing could
creep in and take over an external sub-process command without our
saying so by putting it in a safe, well-known, place. Those days are
gone now. There's little concern for `PATH` safety now (for whatever
reason) but in the process I realized there is a fun way to check your
shell script's external dependencies by just setting `PATH=` to nothing
at the top of the script and watching it fail. Then, you can
incrementally add the directories to that `PATH`. Another cool way (from
@deyloop) is to `export PATH=;` before even running your script. You
could even put that in your scripts tool box as `nopath` and run any
normal command with it instead just to check for dependencies:

```sh
#!/bin/bash
cmd=$(which "$1")
shift
export PATH=
exec "$cmd" "$@"
```

Then try it out:

```
nopath ls -l  # works
nopath foo    # won't work if using any subprocesses at all
```

Related:

* `man bash`

Tags:

    #linux #bash #tips #scripting #coding
