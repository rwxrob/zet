# Using `go.work.off` Convention

After getting burned by `go.work` I've started following a convention of
my own creation for safely managing `go.work` without losing the ability
to save it with my project. After all, it is rather tedious to manage it
all the time. The convention is simple: name it `go.work.off` when you
are not using it. Then create a simple Bonzai command to turn it on and
off:

```go
var golang = &Z.Cmd{
	Name:     `go`,
	Summary:  `go related helper actions`,
	MinArgs:  1,
	Commands: []*Z.Cmd{help.Cmd, gowork},
}

var gowork = &Z.Cmd{
	Name:     `work`,
	Summary:  `turn on or off go.work file`,
	Usage:    `(on|off)`,
	MinArgs:  1,
	Params:   []string{"on", "off"},
	Commands: []*Z.Cmd{help.Cmd},
	Call: func(x *Z.Cmd, args ...string) error {
		switch args[0] {
		case "on":
			if file.Exists("go.work.off") {
				log.Print("go.work.off -> go.work")
				return os.Rename("go.work.off", "go.work")
			}
		case "off":
			if file.Exists("go.work") {
				log.Print("go.work -> go.work.off")
				return os.Rename("go.work", "go.work.off")
			}
		default:
			return x.UsageError()
		}
		return nil
	},
}
```

I've added a main alias `work` for it as well:

```go
	bonzai.Aliases = map[string][]string{
		"work":     {"go", "work"},
	}
```


* [20220325224943](/20220325224943/) Don't Forget to .gitignore go.work
* [20220329053417](/20220329053417/) Burned by go.work. Don't Be Me.

    #golang #coding #tips #bonzai
