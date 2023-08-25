# Config maps are (usually) better than functional options in Go coding

It depends. But usually functional options are confusing and provide less value than a simple configuration map, which is why Kubernetes makes such extensive use of them. I know that Rob Pike and most professional training outfits push functional options. But I mostly hate them. They suck. Use a simple, persist-able, configuration map like the following instead. You know, like Python.

```golang
package C

type Map map[string]any

// ... marshaling and unmarshaling here
```

Functional options claim they are more "sustainable" and "expandable", but at what cost? Functional options are ridiculously hard to follow for most developers, a perfect example of unnecessary obfuscation for no reason. They also require ungodly function argument signatures that span multiple lines forcing them to be put into a slice where a configuration map would have been smaller and simpler to understand.

Functional options also can cause unnecessary performance hits because they must be evaluated to produce a value. Config maps (and the like) are *already* values that don't need any evaluation. There are some isolated cases where functional options are actually faster (such as in the `log/slog` package) but this is usually because these designs *also* accept some other form of argument that has to be coerced into something else before it is used (and functional options always return a value of a specific type already).

People hating on configuration maps always use the example of variadic argument signatures stating that forcing passing an empty map is dubious, then they try to sell you on the exact same thing with a variadic argument slice of functional options. They don't even see that the solution they used with functional options obviously also applies to a configuration map.

```golang

func Foo(c ...C.Map) error {
  // ...
}
```

But an even better solution is to introduce the idea of flexible state with default settings into your struct:

```golang

var DefaultConfig = C.Map{
  `str`: `some`,
  `n`: 3,
}

type Thing struct {
  str string
  n int
  config C.Map
}

func (t Thing) String() string {t.JSON()}

func (t *Thing) JSON() string {
  if t == nil {
    return "null"
  }
  byt, err := json.Unmarshal(t)
  if err != nil {
    log.Print(err)
    return "null"
  }
  return string(byt)
}

func NewThing() *Thing {
  thing := new(Thing)
  thing.Set(DefaultConfig)
  return thing
}

func (t *Thing) Set(c C.Map) error {
  for k,v := range c {
    if k == `str` {
        it, is := v.(string)
        if !is {
          return fmt.Errorf(`str must be string`)
        }
        t.str = it
    }
    t.config[k]=v
  }
  return nil
}
```

Functional options force the separation of option initialization and validation into one function for each option. At first this seems nice since you could import an entire package of options from entirely different packages and maintain some form of composition, but the reality is that usually you want all that validation centralized into a single `x.Set(c C.Map) error` function instead. That way developers creating applications using that struct have a single place to review for every possible option. In fact, spreading the options into separate packages is most definitely an anti-pattern guaranteed to anger and annoy developers using these options.

Functional options also fall on their face when you want to transfer that configuration to anything else, or persist it with marshalling and unmarshalling. In a world of "YAML programmers" this is a show-stopper.

Functional options do allow each option to be documented, but as a function, which is the last place people will look for documentation about command line arguments.

Functional options also force a bunch of unnecessary runtime indirection to call all or those functions where a struct or hash map lookup would be faster.

This isn't Haskell or Lisp, Go can be a functional language for sure, but using them for options is the single dumbest way to promote functional Go (and from the very guy who hated on map/filter/reduce before generics).

<https://dave.cheney.net/2014/10/17/functional-options-for-friendly-apis>

