# What is the fastest way for cleaning a map in Go?

>  for k := range m { delete(m, k) } should work fine.  It will probably be faster to create a new (correctly sized, if you know it) map, but reusing can put less pressure on the garbage collector. (Rob Pike)[^note]

[^note]: Pike, Rob. "what's the fastest way for clearing a map" (2016, August 3). *golang-nuts Newsgroup*. https://groups.google.com/g/golang-nuts/c/UvUm3LA1u8g

