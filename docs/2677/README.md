# Use OSTYPE instead of uname in bash scripts

No need to shell out to `uname` for this stuff.

```sh
#!/bin/bash

if [[ "$OSTYPE" == "darwin"* ]]; then
    echo "Running on macOS"
elif [[ "$OSTYPE" == "linux-gnu"* ]]; then
    echo "Running on Linux"
else
    echo "Unknown OS: $OSTYPE"
fi

```

>   OSTYPE¶
>          A string describing the operating system Bash is running on.

