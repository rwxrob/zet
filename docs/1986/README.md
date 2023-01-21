# PEGN 2023 is so much better than previous version

* <https://github.com/rwxrob/pegn-spec>

First draft of PEGN 2023 is finished and I could not be more pleased. I cannot wait to get it tested and working. Now that `rat/x` is done, converting it over will be a cake walk. In fact, having finished `rat/x` first made me very aware of the best way to convey the grammar in PEGN notation so that it will easily translate to the proper nested results tree from which an AST can easily be created. I think a huge part of that was removing the concept of "significant" from not, which means that every single rule definition is going to produce a result in the tree, so don't do them foolishly.

***The entire spec fits into 142 lines.*** This is because I removed all of the Unicode tables and most of the unused "tokens" (which are just `RRule` and `RRune` now). The `p{..+}` rule notation is a huge game-changer. Anything that can ever be represented in Unicode as a property, class, or script can now be captured with PEGN. Most languages have ways to covering those things so the code generation should be rather easy. God bless Unicode! (Yet another reason to love Rob Pike.)

***Discovered the concept of Rune and Class*** which will be fulfilled as `x.Str` and `x.Is` types.

***Added the `To*` family of Rules.*** These are a massive simplification to the syntax of an grammar specification in PEGN making it much more readable, no more cryptic, excessive negative lookaheads (even though all To rules are implemented as some form of negative lookahead).

***Defining the "any" (.) rule.*** This special rule is implied to be `uprint / WS` for all PEGN grammars, but the magic is that it can be assigned allowing an entire grammar to be taken from a subset of Unicode. This means that if a developer wants to disable line returns in the entire grammar all they have to do is assign only `uprint` or even something more restrictive, like a specific language script. It's a huge breakthrough in simplicity.
