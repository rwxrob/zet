# Only safe way to get "script root" directory

Commands like `rm -rf dist` make some people uncomfortable because if the were executed from another directory (instead of the directory containing the script) they might remove the *wrong* `dist` directory. To get around this people have been inferring the directory containing the script in many different ways, most of them completely wrongly. It turns out that the *only* safe way to get a *safe* script root directory is using the POSIX `dirname` combined with `realpath`.

```
dir="$(dirname "$(realpath "$0")")"
```

Don't forget to quote everything since this is POSIX shell compatible.
