# Check Args with `[[ -n "$1" ]]` Not `(( $# > 0 ))`

It might seem like a good idea to check the argument count, but there's
a good chance it is not what you want. Even a blank argument counts.

```bash
#!/bin/bash

foo() {
  (( $# > 0 )) && echo 'have arguments' && return 0
  echo 'no arguments' && return 1
}

foo
foo ""
foo here
```

Gives you the unexpected:

```
no arguments
have arguments
have arguments
```

Sometimes knowing you got any argument at all can definitely be helpful,
but it is not the common use case.

    #bash #scripting #linux #coding #tips #hacking #100daysofcode
