# Match results are not necessarily AST nodes

While reading through Bruce Hill's excellent and succinct overview of PEG packrat parsing I caught myself wondering why he didn't directly use an AST node to capture the results of a parse function. Then I came to the part where he create the `capture` function. This reminded me that a parsing/scanning match does not necessarily equate to something that should be in the AST. Quite the opposite. I was adding a second begin and end to my results for that capture segment separate from the overall results, but by doing this as its own meta-function, the `Match` struct is not overburdened; it has only a single begin and end. Then, later, I can shake the parse tree of matches to leave only those that have been captured. For me that will be enough to get an AST, but for others, that tree of captures will need to be further evaluated in order to produce a proper AST.

One of the great advantages of realizing this is that it plays well with code generation and the new angle-bracket capture notation in PEGN v2 coming out later in 2023.

* Packrat Parsing from Scratch -- Naming Things  
  <https://blog.bruce-hill.com/packrat-parsing-from-scratch>
