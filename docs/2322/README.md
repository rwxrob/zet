# I still don't like "functional options" (builder pattern)

I'm was warming up to functional options in Go for the specific use case where there are side-effects to setting a value and those values are already candidates for private internal value and using `Set*` mutators. But then I considered the alternatives:

This is a typical function options approach. You have to create a *very* complicated (and completely unnecessary constructor) that only works when a new thing is created.

```go
person := some.NewPerson(
  some.WithName(`Rob`),
  some.WithAge(34))
```

Consider that a simplified constructor with mutators is the same amount of code and much easier to read and write. The constructor here is trivial.  In fact ...

```go
person := some.NewPerson()
person.SetName(`Rob`)
person.SetAge(34)
```

The constructor is complete waste of code. Here's the exact same thing without it.

```go
person := new(Person)
person.SetName(`Rob`)
person.SetAge(34)
```

The *only* reason to ever create a constructor is if there is any chance that some sort of zero-value initialization is required. But we already have a pattern for that.

```go
person := &Person{Name: `Rob`,Age: 34}.Init()
```

This is arguably more dangerous because idiots will forget to read the documentation and extensive examples and forget to call `Init()` (coders are really fucking stupid and lazy most of the time).

Therefore, I'm a fan of the empty (but might need it someday) constructor to avoid possible breaking code changes in the future and the use of `Set` mutators for *every* field in things that are not the most rudimentary of data structs.

## What about persistence?

This is where this whole thing blows up. If you want to persist all of this to a YAML file you now cannot use reflection and tags. Instead, you have to implement `MarshalYAML` and/or `MarshalJSON` and create an identical, inline struct and then use it to populate the actual internal struct.

In practice, this means if I have data that is going to be persisted a lot that I'm not putting that anywhere near my objects with side-effects. One could argue that side-effects are just evil anyway. That makes for more data-centric coding.

For example, I have an SSH user that has an internal `ssh.Signer` set. I can set that at any of a number of places:

1. At construction
1. At `Key` mutation
1. On first use (cached)

The advantage of using the last option is that persistence is absolutely trivial and all the fields can be exported. An interface can always be wrapped around such a thing if and when a consistent interface is needed, but keeping things data-oriented is preferred, for me.

```go
type Person struct {
  Name string
  Age int
}

person := &Person{`Rob`,32} // by far the best

```

## ChatGPT response

There is no definitive answer to this question as it largely depends on personal preference and convention within your project or organization. However, there are some general guidelines you can consider:

1. Use "With" if the option is used to add or modify something.
   - Example: WithTimeout(timeout time.Duration)

2. Use "Set" if the option is used to explicitly set or replace a value.
   - Example: SetMaxRetries(maxRetries int)

3. Consider the naming conventions already used in the Go standard library or popular frameworks that you are working with.

4. Choose a naming convention and stick with it consistently throughout your codebase to maintain clarity and consistency.

Ultimately, the most important aspect is that your option names are descriptive, easy to understand, and follow a consistent naming convention to improve code readability.

