# 💢 OMG! Just use a `[]rune` instead of `[]byte` dummy! (to myself)

I cannot believe how stupid I was to miss this all along. For the last two years I've been writing parsers in Go and completely doing it wrong. I was thinking like a C code the whole time. I forced myself to deal with incoming `[]byte` slices and using long-winded code like `utf8.DecodeRune` and shit. But the entire time all I had to do was coerce the input into a `[]rune` slice instead. I mean, I had dumb convoluted `Pointer` and `Cursor` types just to deal with the varying width of the runes in the underlying `[]byte` buffer and the *entire fucking time* I could have just been using simple integer indexing.

I really feel stupid right now.

For the record, the stuff in the standard library all does the same thing with `[]byte` slices as if they were all thinking C as well. That is where I got the inspiration. And everything written anywhere on the Web also gets it totally fucking wrong. So now I feel like screaming it from the rooftops to help others creating rune scanner *in Go* to avoid all that hassle. After all, this rune-centric view of the data (because Rob Pike was the primary contributor to the UNICODE standard itself) is very much one of Go's unique advantages over *every other fucking language*. So why *not* take full advantage of it?

My code is so much simpler now. It's so embarrassing how much simpler it is. Here's an example:

```go
type R struct {
	Buf        []byte             // full buffer for lookahead or behind
	R          rune               // last decoded/scanned rune, maybe >1byte
	B          int                // index pointing beginning of R
	E          int                // index pointing to end (after) R
	Trace      int                // non-zero activates tracing
}

func (s *R) Scan() bool {

	if s.E >= len(s.Buf) {
		return false
	}

	ln := 1
	r := rune(s.Buf[s.E])
	if r > utf8.RuneSelf {
		r, ln = utf8.DecodeRune(s.Buf[s.E:])
		if ln == 0 {
			return false
		}
	}

	s.B = s.E
	s.E += ln
	s.R = r

	if s.Trace > 0 || Trace > 0 {
		s.Log()
	}

	return true
}

```

And this is the same code after the switch to an underlying `[]rune` slice.

```go
type R struct {
	Buf   []rune // full buffer for lookahead or behind
	Cur   int    // index or current rune in Buf
	Trace int    // non-zero activates tracing
}

func (s *R) Scan() bool {
	if s.Cur+1 >= len(s.Buf) {
		return false
	}
	s.Cur++
	if s.Trace > 0 || Trace > 0 {
		s.Log()
	}
	return true
}

```

But it's not just that code, it is all the other code that was used to grab ranges out of the buffer to return them as AST node content. All of them had to stumble around the variations in position within the buffer because of the variable unicode rune length. Now that is all gone. The `[]rune` indexing just does the right thing.

Don't be me. Just use `[]rune` for your parser/scanners. Hell, it's so easy one almost doesn't even need a helper package for it at all anymore.

At least now I have a *great* "whiteboard" problem to vet the *good* Go programmers. I think I'm finally getting there.
