# Zettelkasten Search Approaches

The way I manage a Zettelkasten-ish repo is as simple as possible
relying on the least amount of technology, in this case minimal bash
shell scripting (with no assumption that `jq` is available). Indeed,
traditional, delimited text files remain the fastest and easiest to read
structured data file format.

## What would I want to query?

We have to have a search engine design that allows the person doing the
search to have the most power. But what would those search queries look
like? Here are some examples:

* Most recently created zettels
* Most recently updated zettels
* Single keyword anywhere in the text of any zettel
* Any of multiple keywords in text of any zettel
* All of multiple keywords in text of any zettel
* Regular expression match in the text of a any zettel
* Any of the above, but just for titles, or headings, or bodies, 
* Any of the above, but only first first paragraph
* Any of the above, but only within code block
* Any of the above, but only within verbatim block
* Any of the above, but only within quoted block

## Searchable Block Scope

Here's a description of the different types of blocks that make up any
[ZettelMark] file. Scopes can be added to queries by combining their
prefix identifiers:

* Title (`t`)
* Heading (`h`)
* Heading1 (`h1`) .. Heading6 (`h6`)
* Paragraph (`p`)
* Code (`c`)
* Verbatim (`v`)
* Quote (`q`)
* Table (`tbl`)
* List (`l`)
* OrderedList (`ol`)
* UnorderedList (`ul`)
* Tags (`tag`)
* Video (`vid`)

[ZettelMark]: /20210812154738/

## Zettel Query Language Syntax

The default query language is simply PCRE, which is activated with `-P`
on modern `grep`. Training users in multiple variations of querying
their data is against their best interests. Perhaps, however, we could
have a configuration variable that sets the query language to use:

* Keyword
* Extended glob
* ERE
* PCRE

Will just support PCRE for now.

Case sensitivity is off by default.

### Combining Query Scope

[Scopes] can be combined together with one another (joined with an
underscore, which is query string friendly) and then finally tied to a
specific query. The order of the scope prefixes determines priority when
ranking and ordering results. To reserve, use exclamation point instead
of equals sign.

Query|Description
:-:|-
`l=foo`|Any list item contains the keyword `foo`
`l!foo`|Any list item that does not contain the keyword `foo`
`ul_ol=foo`|Any list item contains the keyword `foo`, unordered first
`tag=#foo\b`|Tags line contains `foo` hashtag
`h=fo+`|Any heading with matching `fo+` regular expression (PCRE)

Of course, these will all be URL encoded when sent over a web request.

```
tag=#foo
tag=%23foo
h=fo%2b
```

When multiple queries are combined each should be separated by a single
space. Usually this means each query will be a separate argument. When
multiple queries are passed the first query matches will have priority
in the results.

[Scopes]: #searchable-block-scopes

## Optional Tags Line

If the last line of the zettel begins with four or more spaces followed
by an octothorpe (`#`) then it will be interpreted as a *Tags* line/block.

    #tips #zettekasten #streaming
