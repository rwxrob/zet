# PEGs are greedy and blind by default, don't use negative lookaheads

PEGs are greedy and blind by default, that means they eat as much input as they can and they do not consider what comes afterwards:

```
S <- P1* P2 (greedy, blind)
```

That can be considerably easy fixed though by making use of the ordered choice (and without using lookaheads):

```
S <- P1 S / P2 (greedy, non-blind)
S <- P2 / P1 S (lazy, non-blind)
```

Using negative lookaheads (as many wrongly intuit) adds a tremendous amount of unnecessary work.

```
S <- (!P2 P1)* P2
```

In fact, this is done wrong so often that it almost warrants its own PEGN syntax when dealing with "anything up to" patterns.

```
S <- ..P2   # inclusive
S <- ...P2  # non-inclusive
```

* regex - Non-greedy matching in Treetop/PEG? - Stack Overflow  
  <https://stackoverflow.com/questions/1045932/non-greedy-matching-in-treetop-peg>
