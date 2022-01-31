# How are you doing Go automated terminal testing?

It's a combination of several simple shell scripts that run the test
only when an important file changes in the current directory or any
directory underneath it. You can get ideas from the following scripts in
my [dotfile directory](https://github.com/rwxrob/dotfiles):

* [got](https://github.com/rwxrob/dotfiles/blob/main/scripts/got)
* [gott](https://github.com/rwxrob/dotfiles/blob/main/scripts/gott)
* [onchange](https://github.com/rwxrob/dotfiles/blob/main/scripts/onchange)
* [haschanged](https://github.com/rwxrob/dotfiles/blob/main/scripts/haschanged)
* [changed](https://github.com/rwxrob/dotfiles/blob/main/scripts/changed)

Some have suggested I should use the internal Linux events for this, but
I prefer something based on `find` that works anywhere Bash, or even
POSIX shell is installed (which would need some tweaking). 

