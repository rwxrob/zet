# Optimized personal search parameters for KEG and zettelkasten

Search algorithm in KEG is entirely under the control of each individual user. There are not search engines (or corporations) to gatekeep such things. Here are the different semantic divisions and other other criteria that will have a priority weighted score.

* ***Updated*** - last recorded change in `keg-nodes` index
* ***Title*** - words in the title, always first line less than 70 bytes
* ***Summary*** - first paragraph under 400 bytes [500-maxlen(url)]
* ***Lede*** - introductory text of a lede paragraph
* ***Tag*** - tags are maintained in separate indexes
* ***Match*** - patterns and expressions with point adjustments
* ***Popularity*** - each inbound link locally, or from shared KEG cache
* ***Hierarchy*** - how many child nodes, if any
* ...

For any of the categories individuals words can be removed or lowered in priority.

***Match expressions and scoring.*** Mixing in things that provide exceptions and matching for higher priority will be done with any of the three methods of specifying a match expression rule:

* PEGN
* `rat/x`
* Regular expressions (PCRE)

This allows things like command (ex: `!mycommand`) to be excluded completely from the search results, or to be heightened in priority.
