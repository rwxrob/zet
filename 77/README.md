# Amazed How Clear Command Tree Arguments Are

I just have to go off for a bit about how amazing the command line usage
looks for Bonzai commands now that we have full command tree options.
The complexity gets distributed across the branch and because there is
never anything to get in the way, in terms of arguments, you can use
exact counts of arguments as context.

    z gh rel rwxrob/bonzai@latest       - one arg to rel
    z gh rel add rwxrob/bonzai@v0.10.3  - two args to rel

In the above example, the branch `rel` has both a `Call` *and* a
`Commands` list. When the `add` leaf command is noticed it receives the
delegation, otherwise `Call` gets the argument.

This kind of contextual argument stuff is right in the sweet spot
between too overly precise (getopt) and not precise enough, which might
get unpredictable results.

    #golang #coding #bonzai #tips #args
