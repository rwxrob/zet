# Beware of Forked Submodules and `https` Rewrites

We hit an extremely annoying bug today with a submodule that failed to
clone even with `--recurse-submodules` set properly. My best guess is
that it is because it is a fork of another Git repo and fails to do the
`insteadOf` properly. This required removing the following from my
`~/.gitconfig` (which is probably fine).

```gitconfig
[url "git@github.com:"]
	insteadOf = https://github.com/
