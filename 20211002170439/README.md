# DO NOT USE `sync.Map` in Go!

People never read past the first paragraph of the docs. So here is the
rest (which says "never use sync.Map unless you are doing this one
really obscure thing that most never do"):

    The Map type is specialized. Most code should use a plain Go map
    instead, with separate locking or coordination, for better type
    safety and to make it easier to maintain other invariants along with
    the map content.

    The Map type is optimized for two common use cases: (1) when the
    entry for a given key is only ever written once but read many times,
    as in caches that only grow, or (2) when multiple goroutines read,
    write, and overwrite entries for disjoint sets of keys. In these two
    cases, use of a Map may significantly reduce lock contention
    compared to a Go map paired with a separate Mutex or RWMutex.

Tags:

    #golang #tips
