# Bonzai, Vertex and Edge Commands

Bonzai™ command trees, like any rooted node tree, are composed of
*vertex* commands (which aren't really commands, per se) and *edge*
commands (where the work happens). Both can have `Commands` and `Call`
but the `Call` is an edge command is usually far more important. It
might help to draw a command tree (stay tuned, `help tree` command
coming soon to visualize everything). It might help to put a `//vertex`
or `//edge` comment just above your `name := &Z.Cmd{` lines.

    #golang #coding #bonzai #tips
