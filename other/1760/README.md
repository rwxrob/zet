# Use github.com/charmbracelet/glamour for terminal markdown rendering

This is how the `gh`[^1] tool gets the amazing terminal rendering of markdown files. By putting this into the `keg view` command I can avoid `pandoc` dependency, which is why I'm writing my own PEGN grammar for KEGML so that I can create static sites using Go templating without depending on Pandoc's inferior templating system. As a benefit, anyone with either `gh` or `keg` can set `GLAMOUR_STYLE` environment variable to pick their own terminal rendering colors.

[^1]: `pkg/markdown` <https://github.com/cli/cli>
