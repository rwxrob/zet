# Annoying Go Interface Casting Loops

I wish you could cast an entire slice at once. Maybe you can and I'm
just missing something. Until then, the following works but costs
creating an entirely new thing in memory just to get the casting to
work. Here's hoping something optimization-wise is happening internally
by the compiler, but I doubt it.

In this case the value of x.Other is a struct, but the interface can't
know that, so I have to force a cast.

```golang
// GetCommands fulfills the bonzai.Command interface.
func (x *Cmd) GetCommands() []bonzai.Command {
	var commands []bonzai.Command
	for _, s := range x.Other {
		commands = append(commands, bonzai.Command(s))
	}
	return commands
}
```

    #golang #coding #tips #casting
