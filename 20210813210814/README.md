# Zettel Model

The *Zettel Model* describes a zettel as contained within its own
directory (a much more specific version of a KEG Knowledge Node). We'll
use `jq` query notation to give an overview. Requires understanding
ZettelMark as well.

|Identifier|Description|
|:-:|-|
|`.title` |Title heading text (<=50 cols)|
|`.body` |All text of zettel without title|
|`.video` |Video link (if found)|
|`.tags[]`|Tags from the tag line|
|`.data`  |Everything in `data.yaml`|
|`.figure`|Figure related info (empty if no figure)|
|`.figure.height`|Height of figure (if has one)|
|`.figure.width`|Width of figure (if has one)|
|`.refs[].text`|Text of reference (may match `url` or `zet)|
|`.refs[].url`|Fully qualified external Web URL|
|`.refs[].zet`|Internal zettel ID (if has one)|
|`.links[]`|Other zettels that link to this one|

The `refs[].url` is special in that if the reference is nothing but text
it will be returned as a link to the configured external search engine
provider (DuckDuckGo by default).

Creation of `.audio` was decided against since `.video` can be used for
audio only. Besides, `.audio` is best fulfilled by simply having a
natural language processor read back the text content of the zettel.

A `.summary` (first paragraph) was considered and dismissed since the
size of most zettels is too small to warrant it, and we want to
encourage smaller zettels that are the most focused they can be.

A `.figure` name was dismissed because at most a single figure per
zettel and it is always named `figure-<width>-<height>.{jpg,png,gif}`.
