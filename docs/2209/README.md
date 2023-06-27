# Goreleaser will add main.version to golang commands from tags

>    By default, GoReleaser will set the following 3 ldflags:
>       * main.version: Current Git tag (the v prefix is stripped) or the name of the snapshot,
>         if you're using the --snapshot flag
>       * main.commit: Current git commit SHA
>       * main.date: Date in the RFC3339 format

* Using the \`main.version\` ldflag - GoReleaser  
  <https://goreleaser.com/cookbooks/using-main.version/>
