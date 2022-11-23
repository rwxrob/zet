# Needs a universal pager in Go

I've noticed that the `git` application automatically detects a pager and uses it, so does `gh`. And I really want that for the `help` command as well as the `choose` package. But we need something that detects the operating system and pages using it, otherwise uses a built-in, utilitarian, simple pager instead.
