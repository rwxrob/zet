# Just Made Hugo for Go CLI Utilities

I wasn't really purposefully planning it. But by adding template support
for the Description and other fields of Bonzai commands I just created a
way to bundle everything Hugo does for static site generation into a
single Bonzai branch. We're talking portable web sites that are entirely
encapsulated in a single Go binary. I started to have this feeling when
I was reviewing (the rather shitty) Hugo domain language that is allowed
in the templates. You can tell it was really thrown together and evolved
over time. I don't want BonzaiMark templates to suffer the same fate.
The first official builtin template function is `indent`, which takes
into account whatever `Z.IndentBy` has been set to. It is the first of
many I'm sure. When I add support for an embedded fs and full assets
like images, and then an AsWeb of some kind allowing the configuration
of help output to launch the local web browser, well at that point,
we'll have web servers in a bonzai tree, portable, encapsulated trees of
knowledge, which reminds me, all of this would easily carry over into
the work on KEG. In fact, the BonzaiMark that we are using could easily
be the markup for KEG, it's CommonMark and Pandoc Markdown compatible.

    #golang #coding #bonzai #keg #hugo
