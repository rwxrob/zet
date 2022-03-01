# "Mastering Go" Get Generics Totally Wrong

I bought a Packt Publishing book against my better intuition because it
has just so much about some many things, but one look at the following
in the Generics Chapter 13 and I immediately regret my decision:

```go
type Numeric interface {
  type int, int8 // etc.
}
```

Anyone paying any minimal attention to generics in Go immediately can
spot this as a proposed spec that is more than a year old and didn't
make it into the final 1.18 (which I've been enjoying all month). Here's
what *did* make it in:

```go
type Numeric interface {
  int | int8 // etc.
}
```

It's no surprise that glancing at a few other pages reveals how out of
date the book actually is. It's like this guy took all his coding notes
from RedHat and bundled them together quickly after Packt contacted him
to publish a book, which is how all books from Packt get published,
massage an engineer's ego, rush them a book out, massage another
engineer's ego to get them to "review" it, and push it out with no
professional technical vetting of any kind from anyone else. This is why
Packt Publishing books are beyond shit usually.

I'm super sad from this -- especially since I paid money for it. I mean,
there are some good things to read that are covered pretty well, but the
Internet covers them just as well and is faster to query. Hard pass on
this book if you are thinking of getting it.

    #golang #book #reviews
