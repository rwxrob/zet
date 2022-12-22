# Wondering if Go templates would be best for filters and snippets

Currently, most command line UNIX folk will write a quick bash script to take in lines and modify them based on what is being passed. But bash has horrible templating and this approach only works to a point (and is one of the main attractions of Perl to this day). What about Go templating?

Templates have a number of strong advantages:

* Strong logic, but not too much
* Collections of templates and template paths
* Easier than Go to write and maintain
* Super easy to expand with `FuncMap` definitions

What if we created a command that looked up the template in a configured collection and expected standard input that it would process either line by line or as an entire buffer.

```sh
z filter yt.linkify 📺
```

***Base template syntax***

We'd have to come up with a base syntax for the template:

* `lines` - all standard input broken into slice of lines
* `fields` - entire standard input to `strings.Fields`
* `stdin` - raw standard input as string
* `args` - all arguments after the name of the filter
