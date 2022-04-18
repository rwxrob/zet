# Give Go fmt.Stringer a Non-Pointer Receiver

Just noticed something that is not particularly intuitive. When
implementing an `fmt.Stringer` by adding a `String()` method to a struct
in Go so that `fmt.Print*()` does the right thing you need to be sure to
make it *not* a pointer receiver.

```golang
type Foo struct {}

func (f Foo) String() string {return "foo"}
```

If you don't do that then initializations like the following will not do
what you want:

```golang
var foo Foo
foo.Load()     // or whatever
fmt.Print(foo) // prints the Go marshaling, not what you want
```

Now, you might not catch that, though, because a lot people just
create pointers right away, like this:


```golang
foo := new(Foo)
foo.Load()     // or whatever
fmt.Print(foo) // prints your String() output
```

So, moral of the story: *always* use the non-pointer receiver when
implementing fmt.Stringer and GoStringer.

    #golang #coding #tips #stringer
