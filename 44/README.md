# Parser as Struct with Methods is Great

I realized a bunch of unexpected advantages by encapsulating `scan.R`
inside a `Parser` struct. Perhaps the biggest is that all PEGN
identifiers have a one-to-one mapping with their `Parser` methods. This
allows me to document each one. It also allows the creation of node tree
constant integers in the same `mark` namespace without naming
collisions. For example, `Tag` and `p.Tag()` are separated.


```golang
func (p *Parser) Tag() bool {
	p.S.Scan()
	if p.S.R != '#' {
		p.S.P--
		return false
	}
	beg := p.S.P
	var n int
	for p.ULetter() {
		n++
		if n > 20 {
			p.S.Error(TagTooLong{})
		}
	}
	if n > 0 {
		p.add(Tag, beg)
		return true
	}
	return false
}
```

Returning boolean from the parsing has also got to be one of the
smartest accidental things I did. It means that I can loop over the
methods just like `s.Scan` in the scanner.

```golan
for p.ULetter() {
  ...
}
```

That code gobbles up all the `ULetters` until it hits something that isn't
one, including end of data. That ability to gobble up a bunch of stuff
in a simple `for` loop really feels great. So glad that worked out.

    #golang #coding #tips
