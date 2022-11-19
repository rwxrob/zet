# Process for Specifying KEG Type

I did some work on this a long time ago. But we just need a unique way
to identify any new KEG Type specifications, and hopefully create
versioning of it so that tool creators can support the type.

KEG Types are fundamentally about assigning semantic meaning, syntax,
and file organization for a KEG Node above and beyond the minimum
requirements for *any* KEG Node (directory with `README.md` in KEG Mark
and/or `data.yaml`).

KEG types and Kubernetes types can steal from MIME type rules, sort of:

* KEG URL to authoritative node with `<domain>/KEG/types/<name>/README.md`
* Name can be any characters matching `[a-Z0-9.-]{3,30}`

Standard types will be added to `keg.pub/KEG/types/<name>/README.md`
after they have become quite mature. The same process of "sandbox",
"mature" and such used by Kubernetes will be used for submissions of KEG
types so that more than a specific, single decision body controls.

A KEG type should specify things like the following:

* Semantic constraints on reserved `README.md` file
* Schema of reserved `data.yaml` if any
* Number and type of files allowed in KEG Node directory
* Subdirectory constraints and purpose
* Generator rules (ex: `gen.go`)

    #keg #spec #types
