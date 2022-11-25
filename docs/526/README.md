# Count Total Weeks from Vim with Bash Filter Script

Was just working on the schedule for the Beginner Boost and needed to
know how many weeks I was actually planning by totalling up all the
lines with `(n week(s))` in them. Just the sort of job for Vim and
UNIX filters!

```bash
#!/bin/bash

weeks=0

while IFS= read -r line; do
  echo "$line"
  if [[ $line =~ \(([0-9]+)\ weeks?\) ]]; then
    ((weeks+=${BASH_REMATCH[1]}))
  fi
done
echo
echo "TOTAL: $weeks"
```

Related:

* [20210809223847](/20210809223847/) What is a UNIX/Linux Filter?

Tags:

    #linux #unix #filter #philosophy #vim #scripting #coding
