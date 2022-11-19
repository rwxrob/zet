# STOP `cat`-ing Into Stuff in Shell!

Be really sure you know why using `cat` in the following example is dead
wrong and downright unsafe.

```
#!/bin/bash

declare count=1

# WRONG! (count is shadowed by subshell)
# cat /tmp/bar | while read line; do
#   echo "$count $line"
#   ((count++))
# done

while read line; do
  echo "$count $line"
  ((count++))
done < /tmp/bar

echo "Should be 3: $count"
```

Tags:

    #linux #bash #secops #scripting #coding
