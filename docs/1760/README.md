# Use github.com/charmbracelet/glamour for terminal markdown rendering

This is how the `gh`[^1] tool gets the amazing terminal rendering of markdown files. Thinking of putting this into the `keg view` command and completely avoiding any `pandoc` dependency, which is why I'm writing my own PEGN grammar for KEGML so that I can create static sites using Go templating without depending on Pandoc's inferior templating system.

[^1]: `pkg/markdown` <https://github.com/cli/cli>
