# Bonzai, Vertex (Branch) and Edge (Leaf) Commands

Bonzai™ command trees, like any rooted node tree, are composed of
branches, or *vertex* commands (which aren't really commands, per se)
and leaf commands on the outer *edge* (where the work happens). Both can
have `Commands` and `Call` functions but the `Call` is an edge command
is usually far more important. It might help to draw a command tree
(stay tuned, `help tree` command coming soon to visualize everything).
It might help to put a `//branch` or `//leaf` comment just above your
`name := &Z.Cmd{` lines.

    #golang #coding #bonzai #tips
