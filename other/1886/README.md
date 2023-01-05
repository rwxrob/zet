# Almost dropped `rat.Result.R` because annoying, but we need it

As annoying as it is to pass the `r []rune` reference to `Result{R:r}` in every `CheckFunc` it saves us from bigger annoyances later, like having a result become decoupled from the parent results to which it belonged.

For example, say we create a filter function that walks the results tree to find only the single result that had a specific tag --- a very likely use case. That returned result would lose the `R []rune` to which the `B` and `E` refer. At that point the user of the `rat` package would have to tape together the slice that was passed into the result in order to produce a valuable marshaling of that result tree. No result tree is worth anything without containing the data to which the pointer results associate.

So crisis averted, `R` MUST be assigned by ever `CheckFunc` (or it's simply not qualified to be a `CheckFunc`). It would be too much to assert that any `CheckFunc` or `Rule` passed to `Pack` fulfilled this (although technically possible) but having a utility function to validate this might be nice for those writing tests.
