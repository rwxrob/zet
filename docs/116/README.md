# Use Go `internal` to Not Export Symbols

I suppose I've never worked on a big enough project to care about the
implications of too much public API exposure, but I certainly appreciate
the concerns of large projects to protect themselves from such tight
coupling that could ensue. Well, I was today-years-old when I learned
about `internal`. I was, like, "What the fuck is up with all the
`internal` subdirectories in this Kind dependency path? Now I know why.

The `internal` directory is specifically known to the `go` compiler
(like `testdata`) and nothing in it can be used by anything that doesn't
"share an ancestor" meaning, that things are "internal". You can always
start with it and put everything in there and then just promote it later
if you need.

Perhaps the biggest advantage is that you can name stuff as you would
anywhere else, even avoid the problem with tagged JSON/YAML by leaving
things "public" but in the `internal` directory.

* Use internal packages to reduce your public API surface \| Dave Cheney  
  <https://dave.cheney.net/2019/10/06/use-internal-packages-to-reduce-your-public-api-surface>

    #golang #tips
