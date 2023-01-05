# Extended ZettelMark, for Academia and More

Extended ZettelMark is nothing more than ZettelMark with LaTeK. While
ZettelMark is purposely very constrained to help authors best congeal
and convey their ideas, sometimes it is necessary to represent things
that CommonMark just cannot handle, such as mathematics. The academic
world has long since solved this issue with LaTeK, the de-facto standard
for academic publishing and the unofficial main *additional* language to
Markdown supported by Pandoc Markdown, (which is so standardized it was
chosen as the official documentation language of the R programming
language). The Golang goldmark Markdown parser also supports LaTeK by
way of KaTeX math.

Keep in mind that by using Extended ZettelMark that GitHub will be
unable to render your LaTeX extensions when viewing your files from
their web interface. 
