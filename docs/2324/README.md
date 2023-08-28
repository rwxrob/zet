# Zero-value-safe structs are always better than constructors

Go isn't Java. Go isn't C++. Any struct should *always* be created so that anyone can use it with `new(Struct)` safely for all it's methods and passing it into anything. That's the entire fucking point of zero-values in Go.

"Zero ... wha?"

Yeah, so many developers have no fucking idea how to code Go and make stupid assumptions from their idiotic languages they have been raised on. Go's zero-value focus is one of the most brilliant parts of the language. It means that everything is simpler--especially marshalling and persistence.

I'm getting pretty sick and tired of all the OOP disease infecting so much Go code. In fact, ChatGPT even says that using `Init()` is not preferred versus `New*()` constructors. While it is true that `New*` is used as an idiom in *some* of the standard library code almost all cases prefer the use of structs where the default zero value is safe. In cases where initialization (or re-initialization) is desirable the long-standing best practice has always been to add an `Init()` without breaking the safely of the struct's zero value.

