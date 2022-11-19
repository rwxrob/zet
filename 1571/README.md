# Bonzai `fmt` Branch, Empower Shell with Go `text/template`

As I've been adding `text/template` support to most all of the fields of
any `bonzai.Command` I realized that we have all the code necessary to
implement a `mark` Bonzai branch, and to factor all the BonzaiMark stuff
out of the `bonzai` package. I'm already excited about the possibility
of `z mark ...` to create amazing reports and other output. In fact, I
need this before I do `z zet` and `z keg` because I can use that instead
of pandoc for sure. Pandoc is great, but it's templating absolutely
sucks. But everything sucks compared to Go templating.

The `fmt` branch will be *only* template formatting with no additional
markup handling. Some people will want their own Markdown. In fact, it
makes sense to keep `mark` *only* BonzaiMark and `fmt` only template
replacement, then we just pipe the one into the other ( `z fmt file
foo.md -- mark`)

In fact, the new template functions will be very useful from a generic
sense:

* `{{ conf "foo"}}`
* `{{ var "foo"}}`
* `{{ exe "ls" "-l" }}`
* `{{ json "file|http|conf|var|exe" ".jq.query" }}`
* `{{ yaml "file|http|conf|var|exe" ".yq.query" }}`

These would be relative to the `Caller` of the `md` command. By being
able to use `var set` for things so many things are possible. Obviously,
templates must only be allowed from a trusted source.

This makes me very happy since it is perl formatted output but so much
better. Generating reports and static HTML sites will be a breeze.

    #golang #bonzai #fmt #markdown #plans
