# PEGN grammar caching supports minimal possible grammar specs

The more I get this packrat parser and `Grammar.Pack` method working the more I realize that having an all encompassing grammar is actually not the way to go because of the unnecessary additional overhead or packing unneeded stuff into the `Grammar` will have on cache hits during rule lookups.

It still makes sense, however, to allow for libraries of standalone `Rules` that don't require knowing about the caching capabilities of any grammar. The rule generating helper functions will always have value for this.
