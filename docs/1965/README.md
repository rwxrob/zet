# Conflicted about `rat/x` result naming in parse tree

I'm wondering if using a unique integer is better than an actual string name. Pandoc has no problem including the full string, even for something like `Space`. This creates incredibly verbose AST results:

```json
          {
            "t": "Str",
            "c": "Scanner-less"
          },
          {
            "t": "Space"
          },
          {
            "t": "Str",
            "c": "PEG"
          },
          {
            "t": "Space"
          },
          {
            "t": "Str",
            "c": "packrat"
          },
          {
            "t": "Space"
          },

```

In fact, the old style of only including the tokens in the AST that comes out of the Pandoc command is really broken in 2023. This provides no workable data from which to quickly assimilate what the original looked like.

I understand why Pandoc is so verbose. Some situations would make including the entire text very wasteful because only a few tokens might exist within it. `rat/x` makes some modern assumptions about how much of the data being parsed is still relevant when including the entire original document every single time. This makes `rat/x` somewhat unique. I have never run into any parser that uses the same strategy even though it is beautiful in how it enables multiple, even overlapping parsing against the same data. All the "parse" results are just pointers into that data which is included in ever result tree.

But there is a problem with using integer identifiers. They have to be mapped back to string names somehow and the results themselves do not have that lookup table included. I could make it so that every result has a back-reference to them (as it does for the `[]rune` slice). Or I could even back reference the entire grammar from which the result was parsed. These approaches save tremendously on the size of the resulting parse trees when represented as JSON data.

Another approach, like Pandoc, is to just include the names in the results rather than the integer. This is orders of magnitude greater when dealing with grammars that have a lot of named results, but most don't, most just want one or two named things that they can call out of it. This approach also saves the user of the tree from having to go through the complicated task of looking up those integer identifiers.

I suppose I could have them both: `x.Name` and `x.ID`. That way the person writing the grammar can decide which to use. That's what I'll do. Then, I'll just `omitempty` on the JSON output.














