# Bash to Go Pain Point: Pipes and Filters

The reason Bash is by far my favorite language is because of how fast
you can create things. The UNIX philosophy and UNIX filters are the
dominant approach to modern computing. So when you look at how to do the
same thing as a simple `|` in bash in Go you will at least frown a
little. It's a pain in the ass. This is where functional languages
really win. I'm not giving up hope though, I'm thinking some of this can
be abstracted into what I'm looking for.

```go

func that(in any) any {}
fn.Pipe("this",that,other )
```

Rob Pike addresses this in the Go template language, which has full
support for pipes and even used bar `|` notation. He requires that they
be "niladic" functions returning nothing but a string and optional
error. But they have control of the argument of each one. I need
something more generic that takes it's input as a string and returns a
string.

I think we can do this with the `any` type and assume everything can be
converted to a string form (`fmt.Sprintf`)
