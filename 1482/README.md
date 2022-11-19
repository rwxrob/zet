# Personal Go "Awesome" List

Now that I'm breaking everything out into its own package (which makes
all the naming to much cleaner) I have to sort of join all that work
back together to keep track of it and know where a new utility should go
when I create a quick and dirty one. The new "awesome" list is that for
me.

In effect, the "awesome" list is the equivalent of my scripts directory
for bash stuff. I am constantly adding new filters and utilities in
there with little thought about organization. I can just grep it and
find what I need after I forget about something. But the equivalent
approach to Go programming is not only not "idiomatic" it's just plain
ugly and unwieldy. The solution is maintain a core manifest of all those
packages so that you don't end up with a single catch-all `util`
package, which is very specifically *not* idiomatic Go (and the reason
`ioutil` was split up and deprecated).

* <https://github.com/rwxrob/awesome-go>

    #golang #organization #coding
