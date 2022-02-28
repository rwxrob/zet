# Build for All Go Architectures

Here's a little script for building any Go program for all supported
target architectures:

```bash
#!/bin/bash

# Builds the passed Go package or command for every supported operating system and architecture into directories named for such and logs.

godistbuild () {
  declare relpath="${1-.}"
  declare log="$PWD/build.log"
  >| $log # truncate
  for dist in $(go tool dist list); do
    [[ ! -d $dist ]] && mkdir -p $dist
    declare os=${dist%/*}
    declare arch=${dist#*/}
    echo "BUILDING: $os-$arch" | tee -a $log
    cd $dist
    GOOS=$os GOARCH=$arch go build $relpath  >> $log 2>&1
    echo >> $log
    cd - &>/dev/null
  done
}

godistbuild $*
```

    #golang #tips #coding #tools
