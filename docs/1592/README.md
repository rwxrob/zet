# Use `command -v` Instead of `type` (Not POSIX)

> `type` is not required by POSIX

Up until today I thought `type`  and `which` were POSIX. Apparently, they are not. Thanks to our good friend Juan on the live stream who is dutifully using `shellcheck` to look at everything we now know that `which` was never POSIX and that `command -v` should be used instead. We tested all variations of `type` and none of them with options are POSIX either even though I've always used `type` to check for the existence of something since it looks for aliases (and exported functions in Bash) but looks like `command -v` from now on for everything.

Note that `command -v` returns positive for functions and aliases as well as executables in the PATH. It seems that `which` is the only way to identify PATH commands.

* Is \`command -v\` option required in a POSIX shell? Is posh compliant with POSIX? - Stack Overflow  
  <https://stackoverflow.com/questions/34572700/is-command-v-option-required-in-a-posix-shell-is-posh-compliant-with-posix>
