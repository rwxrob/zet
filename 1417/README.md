# Use `[[ ${foo[key]:+exists} ]]` in Bash for Map Keys

Sometimes you want to check if an associative array has ever had a key
defined --- even if the value is empty. Use the parameter expansion 'if
unset or null' notation allows for this when combined with bash
double-bracket conditions.

```bash
#!/bin/bash

declare -A map
map[foo]=FOO
map[bar]=BAR
map[empty]=

for key in foo bar empty other; do
  [[ ${map[$key]:+exists} ]] && echo "$key exists"
done
```

Related:

* Bash Manual (`man`) Page - Parameter Expansion

Tags:

    #bash #tips #maps #dicts #associative #arrays
