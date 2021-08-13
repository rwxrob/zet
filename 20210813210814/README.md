# Zettel Data Model

The *Zettel Data Model* describes a zettel as contained within its own
directory (a much more specific version of a KEG Knowledge Node). We'll
use `jq` query notation to give an overview. Requires understating
ZettelMark as well.

Everything in the `data.yaml` file is accessed with the `.data` prefix.

Everything in the `README.md` can accessed with the `.doc` prefix and
includes the following automatically:

|Identifier|Description|
|:-:|-|
|`.title`|Title heading text (<=50 cols)|
|`.video`|Video link (if found)
|`.main`|First paragraph block
|`.tags[]`|Tags from the tag line

