# Beware of Go `path.Join` vs `filepath.Join`

Note that `path.Join` only joins with a "slash" whereas `filepath.Join` uses the OS-specific path separator. They are *not* the same. In fact, most people should just completely forget that `path.Join` even exists at all.
