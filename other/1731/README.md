# Bonzai `grep`: stateful, concurrent, faster than UNIX, composable

We started out wanting something simple for searching to add to `keg` until we get true `fts` support (full-text-searching). Just plugging `grep` seemed like the best option at first, then as we got to looking into it, turns out that creating a better, concurrent version of `grep` with full Go regular expression support is actually not only relatively easy, but would enable a `z grep` command that can be pointed at any directory or file and include stateful configuration of pre-filters, maximum concurrent goroutines, color output preferences, and more. This stateful grep stands to be be several orders of magnitude better than then old, broken, non-concurrent `grep` comment. The fact that it can be composed into any [stateful command tree monolith](/1729) just makes it all the better.

*Stay tuned to this zet content node (1731) for updates.*
