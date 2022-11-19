# Dash, Ash Support `local`, But Not POSIX

Thank God for `shellcheck` reporting `local` is not POSIX. It's
virtually impossible to determine that any other way right now since
`dash`, `ash` (including BusyBox), and `bash --posix` all allow it
without any error or warning. Not everyone has an AIX or Solaris box
around the house. I don't (any longer). I imagine this is `ksh`'s fault.
