# PEG packrat parsing requires memoization with `map` in Go

The more I get into the packrat parser implementation in Go the more I realize it cannot be done properly without a hash map to contain the memoized closure functions.

The key (for me) to understanding this is walking through the repetition that would otherwise happen without it to compile the functions.

```pegn
Doc       <- Title / List / Para
Title     <- '# ' rune{1,70} EndBlock
List      <- ('*' / '+' / '-') SP print+ EndBlock
Para      <- print+ EndBlock
EndBlock  <- end / LF end / LF{2}
End       <- !rune
```

This grammar cleanly takes care of the memoization just by the organization of the rules, but technically it should still memoize even if there were not an `EndBlock` (for example).

```pegn
Doc       <- Title / List / Para
Title     <- '# ' rune{1,70} LF{2}
List      <- ('*' / '+' / '-') SP print+ LF{2}
Para      <- print+ LF{2}
```

This isn't completely accurate, but it makes the point. Without memoization the compiled function to handle `LF{2}` gets created three times even though all three functions would do the same thing.
