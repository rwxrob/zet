# Go doesn't require `implements` declaration

One of the least known or appreciated advantages of Go over languages like Java and C++ is that the development doesn't have to know about an interface that it fulfills. In fact, often a struct might end up fulfilling an interface without even knowing it.

Take the `fmt.Stringer` interface, for example. Just add a `String() string` method and boom, you are done. Your struct can now be passed into anything that accepts a `Stringer` type (and there are vary many things that do). Now imagine doing that same thing in Java. Every single class would have to include `implements Stringer` along with the dozens of other interfaces. Go does require that at all.

This design decision is one of those subtle but substantial points of objective evidence that Go was *designed* to be amazing, not some accidental success. The entire idiomatic approach to interfaces is absolutely brilliant, but only experienced polyglot developers (who have been burned by all the alternatives) will even *notice* advantages such as this.
