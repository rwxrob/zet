# Use initial underscore for constants, `snake_case` for embeds

These simple conventions make code that needs to be internationalized (which should be every code base) very easy to quickly scan, understand, and internationalize.

```go
const _FileNotFound = `file not found: %v`

//go:embed desc/en/foo-sub.md
var _foo_sub string
```

Adding an initial underscore to any constant or string identifier that contains natural language that might need translation is a good convention to use within new Go code bases that don't already have a lot of crufty misuse of underscores. It makes these identifiers immediately standout. They are searchable with simple regular expression matches against the code base. And they play nice with the other variables.

In addition, any string that has been embedded uses `snake_case` to match the hyphenated equivalent in the proper language directory named according to the universal language identifier.
