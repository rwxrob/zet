# Bonzai and Cobra in same repo?

Now that I know Cobra can be coerced into importing remote command trees it occurred to me that putting both a Bonzai and Cobra importable command tree, or collection of importable commands, into the same Go module is completely doable. This provides the distinct advantage of using the same internationalized, embedded text strings for both that could be altered with a single `generate` directive somehow in `goreleaser`.

One blocker is Cobra's absolutely ugly documentation. The method is tightly coupled within stupid function calls completely unnecessarily. Cobra completely discards the obvious opportunity to leverage Go's power templating package for command documentation.

No. The answer is No. So long as the business logic is in its own package and well documented in English the other modules containing the commands that import that logic can be made specific for a target use base. This also puts the focus back on the functionality and not the framework using it.
