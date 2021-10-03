# Consider Not Using `encoding/json` in Go 

The built-in JSON library (including the tagging of structs that forces
the use of reflection) is really quite bad. My biggest gripe is how it
forces all Unicode code points to be escaped even though they are
completely valid JSON values. Here's a list of some alternatives:

* <https://github.com/json-iterator/go>

Here's a way to give people the option of using the built in versus the
faster one:

```
go build -tags=jsoniter
```

Tags:

    #golang #json
