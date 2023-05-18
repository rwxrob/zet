# Always use sed -r for regular expression consistency

The `-r` and `-E` options to the `sed` command are equivalent on every version of the command on all versions of UNIX. But `-r` seems to be supported by more of them. This is because if the version of `sed` is very old then you are probably using BSD or some derivative which has supported the `-r` option longer.

This enables extended regular expressions (like Perl) so you don't have to fight with all the problems with basic regular expressions, most notably the escaping of all the special characters like parenthesis and bar.

It's probably worth it not to put this into an alias to keep reminding yourself that it is needed instead of expecting it on a foreign system and wondering why `sed` is "broken" on that system.
