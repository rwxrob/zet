# Decided on Commenting Personal Go Rules

After continuously going back and forth on whether I should use a
semi-blank line preceding signatures in Go inline commenting, I've
decided to only add it if there are more than two comment lines.

```golang
// Foo prints foo.
func Foo() { fmt.Println("foo") }

// Foo prints foo an the origin of foo is something some people
// attribute to fubar going back to the days of the war.
func Foo() { fmt.Println("foo") }

// Foo prints foo an the origin of foo is something some people
// attribute to fubar going back to the days of the war. But others are
// convinced it had nothing to do with that.
//
func Foo() { fmt.Println("foo") }
```

    #golang #conventions #comments
