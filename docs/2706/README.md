# Always separate business logic from tools that use it

I have been burned so much by giving into the lazy practice of mixing a command with the high-level, importable package containing the core business logic that I want to make available to those building their own software. Ironically, many developers who are making extensive use of web APIs in order to avoid tight-coupling to any specific implementation have no problem violating this principle within their Go modules. It's the same thing.

An example of this would be having both a `pkg` and `cmd` directory in the same project (or equivalent). Almost always any such project should be split in two with one repo/module with the `pkg` stuff (`package foo`) and another one with a `cmd` directory containing one or more commands that use other things (`package main`).

Splitting allows anything to build dependencies to the business logic package (`package foo`) without ever pulling in all the crap from the `cmd` directory.

Splitting also allows utilities to be constructed using absolutely different frameworks (Cobra, Bonzai, Gin, Echo). All of these can *share* the same core business logic without caring about the others. I once considered adding a `cmd/bonzai` and `cmd/cobra` along with the business logic at the top level. Then I broke out the command from the business logic package.

Having this separation allows the absolutely brilliant possibility to invoke the same functionality either through a web application talking to an API or directly from a compiled command-line utility.

Some might argue that all command-line utilities *should* invoke the API endpoint instead. Fine. Either way, having the business logic (and only the business logic) managed in its own repo/module prevents the brittle coupling that so many projects fail to avoid (to their peril).

NEVER put more than one Go module into a single repo EVER! FUCK MONO REPOS! THEY DO NOT PLAY WELL WITH GO---especially when GHEC is involved.

You projects suffer from this all the time. The GitHub CLI tool `gh` (which I absolutely love) has completely doubled down on the Cobra framework and made "Factories" to generate all the commands and subcommands that reside right next to the actual "business logic" that does the work. It's some of the most disgusting code I have ever seen. This is an extremely short-sighted approach.

Command-line frameworks come and go as fast as web frameworks in the webdev universe. Corrupting all your business logic with a cancerous ganglia like Cobra is almost as bad as hard-coding a dependency on a specific API middleware. It's just only something someone with absolutely no long-term development experience ever does. But even we veterans get sucked into it on occasion, usually out of laziness (which is also what brought us the "mono repo" anti-pattern, thank God I was never gave in to that).

