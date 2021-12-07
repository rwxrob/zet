# Splitting Out Arrays from Another Array in Bash

```
mapfile -t values < input
echo "${values[@]:0:3}"
```

Tags:

    #bash #linux #tips #adventofcode
