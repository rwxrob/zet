# Always Return Errors in Go

I just got un-burned by fixing something that didn't feel right in my
`rwxrob/conf` design. I was just printing the errors with `log.Print`
instead of returning them. Yeah, that was stupid. I broke a lot of code
adding all the errors back, but it's a great reminder that --- like 'em
or hate 'em --- two-value returns are pretty much the standard in Go, so
much so that even the `text/template` package is aware of them. (You can
return exactly one thing, a string or a string and an error.)

The good news is that I was immediately able to see an error that was
being generated deep in one of my YAML parsing dependencies just because
I started returning them in the `conf` package that used it. 🤦

    #golang #coding #tips
