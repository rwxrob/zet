# Use `read -rs -p 'Password: '` to read password from shell

Turns out the `-s` is compatible with Alpine (and probably POSIX). This is much easier than `stty -noecho` and trapping possible breaks from that.
