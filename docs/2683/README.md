# So important to use Go `os.UserConfigDir` (not `$XDG_CONFIG_HOME`)

Macs are UNIX, not Linux, but Go gets it right. This is even more evidence that creating command line utilities in Go is really the overwhelming best practice in 2024. There is simply no reliable way to obtain this information consistently across all operating systems in *any* other modern language.

It follows that creating your favorite utilities in Go instead of even shell is really the way to go (lol).

This, in turn, argues for creating Bonzai command trees that are in a single monolith binary that can easy be transported to any target host instead of in hundreds of disparate shell scripts, even with `git clone` making it easier.
