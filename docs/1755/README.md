# Q: How are you testing Go when files change?

I'm using `entr` in the following one line shell script:

```sh
#!/usr/bin/env bash
entr bash -c "clear; go test $*" < <(find .)
```
