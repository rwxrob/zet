# Casting Go Slice to Interface Requires Loop

Wrong:

```go
func (x *Cmd) GetCommands() []comp.Command {
  return []comp.Command(x.Commands)
}
```

Produces the following error:

```
./cmd.go:170:68: cannot convert x.Commands (variable of type []*Cmd) to
type []comp.Command
```

But if you start with a list of the right type (`comp.Command`
interface) then you can add to it and it just works.

Right:

```go
func (x *Cmd) GetCommands() []comp.Command {
	list := []comp.Command{}
	for _, c := range x.Commands {
		list = append(list, c)
	}
	return list
}
```

