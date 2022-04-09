# Ideas for Bonzai CacheMap Interface

The `CacheMap` will be a critical requirement for Bonzai to really take
over the `getopt` zombie-land --- especially once pipe (`->` the other
equivalent ligature).

```go
type CacheMap interface {
  Var(key, type string)
  Type(key string) string
  Get(key string) string
  Set(key, val string)
  Del(key string)
  String() string // YAML key: value
  Print()         // print YAML
}
```

And the equivalent `z` commands in a Bonzai branch:

```
z var type <typestring> <key> [<value>]
z var [set] <key> <value>...
z var [get] <key>
z var del <key>
z var all
```

The `Var` allows Cacher implementations to create their own types with
different considerations like `encrypted` or `performant` so that it can
make the best decisions about how to deal with `set` and `get` later for
it even though everything is just a string so far as the user is
concerned. Most would just use the default plain `string` type, which we
should probably mandate in the interface spec must be reserved and
supported. After all, everything here is a string (in the truest of UNIX
philosophy compliance).

* Single file Protobuf default implementation in `os.UserCacheDir`

I think I've decided that any Bonzai monolith can have one (and only
one) Cacher per binary that uses the Bonzai package, exactly like Z.Conf
there will be a Z.Cache with Set/Get/Var/Type methods. People don't have
to assign a Z.Cache, but those that do get *both* the Z.Cache commands
to use in their Cmd code as well as whatever commands they choose for
it (the default will be `z var`).
