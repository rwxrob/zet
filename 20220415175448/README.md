# BonzaiMark in PEGN and/or `goyacc`?

The popular `yacc` tool has always suffered from serious design
problems, even though it has been the go-to tool for creating
lexers/parsers in C for more than 30 years. I just ran into it again in
`goyacc`, which enabled `gojq` to exist. I absolutely love that project
and their decisions and the performance looks solid so far. So I'm
facing something of an internal dilemma. I have to implement the parser
for BonzaiMark and I can use either one. The thing with `goyacc` is that
you don't get an AST out of it (at least I don't think). With PEGN I
could. In fact, PEGN is closer to regular expressions than a highly
optimized parser. I could, perhaps, make the first PEGN parser in
`goyacc` and then use it to generate a better one in all Go, that is the
advantage of PEGN is that *any* language can be represented in it (like
Antlr in Java).

I've not done a full grammar in `yacc` ever, even though I once owned
the `yacc`/`bison` O'Reilly book. But I have to admit, I'm feeling
really obsessed with learning it and doing it. That same feeling I've
had about other things in the past, and then it faded after I mastered
it. I really want to do it once to see the advantages and disadvantages
versus PEGN, EBNF, ABNF and others.

There's just not enough time!! So many things to learn and play with in
life. How people ever get bored or don't have any ideas on what to do or
make is completely beyond me. I'm actually tense now because I want to
clear my plate to play with `goyacc` of all things. Most people will
just think I'm one fucking sick puppy. Oh well.

    #yacc #parsers #lexing #golang #coding
