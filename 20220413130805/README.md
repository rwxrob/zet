# Go Anonymous Struct Gotchas

Just ran into a very weird problem that I do not understand at all. I
just accept the resolution for now. It involves dealing with anonymous
structs (which, I'm discovering, are far more magic than I have ever
appreciated).

The following Bonzai `Call` (from `web`) works:

```go
	Call: func(_ *Z.Cmd, args ...string) error {
		data := &struct{ Name string }{}
		req := web.Req{URL: args[0], Data: data}
		if err := req.Submit(); err != nil {
			return err
		}
		fmt.Println(data.Name)
		return nil
	},
```

Here's the output:

```
$ web get https://api.github.com/repos/rwxrob/z/releases/latest
v0.2.2
```

This one doesn't:

```go
	Call: func(_ *Z.Cmd, args ...string) error {
		req := web.Req{URL: args[0], Data: &struct{ Name string }{}}
		if err := req.Submit(); err != nil {
			return err
		}
		fmt.Println(req.Data.Name)
		return nil
	},
```

It won't even compile. Can't resolve the `Name` field for some reason:

```
./web.go:56:24: req.Data.Name undefined (type any has no field or method
Name)
```

I've tried lots of iterations on this with different casting. Nothing
seems to work. But setting the var to the anon struct early on does
work.

By the way, you cannot define an actual struct type within a `Call`
because Go doesn't allow anything but anonymous anything within
function/method block (and for good reason, otherwise people would
dynamically change types and methods all over the place).

    #golang #coding #tip #structs #anonymous
