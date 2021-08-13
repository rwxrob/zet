# EzMark: Simplified CommonMark + GFM Tables

EzMark is CommonMark + GFM tables with the following constraints making
it drop dead simple to learn and parse — even from shell scripts.

* Make the source as readable as possible by itself
* Front-matter (YAML, etc.) has never been allowed in CommonMark
* Only one first level heading in the file
* First level heading *must* be on first line
* First level heading must only have a single space after `#`
* Keep headings descending incrementally (not `##` -> `####`)
* Use only ATX style headings (with `#`) not Setx (`foo\n---`)
* Never indent (even though CommonMark allows "up to three spaces")
* Use `*`,`**`,`***` only for italic, bold, bold italic
* Use `1.` only for ordered lists
* Only use a single space after list item marker
* Use `----` only for separator / horizontal rule
* All blocks *should* be wrapped to 72 columns
* Use `\`\`\`foo` fences only for code blocks
* Use `~~~foo` or `~~~~foo` only for code block contains conflicting
* Use plain `\`\`\`` as non-specific code block
* Use two or more trailing spaces for hard breaks
* Just links in link destinations (no hover text)
* Understand code blocks will be snipped when "codeless" applied
* Use Verbatim (4+ initial spaces) for poetry, addresses, art etc.
* Always use angle brackets for URLs `<https://rwx.gg>`
* Use either inline or reference links
* Always include angle brackets around URLs in text
* Include angle brackets around URLs in reference links
* No strikethrough allowed (unsupported by CommonMark)
* Use `> ` for quoted blocks and wrap if you can
* Use `> 😄` with emoji on single line to start EmojiBlocks

Also consider:

* [20210812154738](/20210812154738/) ZettelMark, Simplified, Semantic CommonMark
