# Use `README.md` and `data.yaml` for Consistency

One of the practices that really stuck from all the KEG work I did last
Summer is the use of consistent file names and formats for *knowledge
nodes* (sometimes called *KEG nodes*). This simple convention when
combined with simplified Markdown (KEG Markdown) and some consistent
field names in the `data.yaml` makes for powerful automations and
queries just from the raw data itself.

## Naming Justification

The `README.md` name has become the default for almost all GitHub repos
and is created automatically from the GUI when using it. It is the
`index.html` of the Markdown world.

The `data.yaml` file, which may contain JSON data since JSON is a formal
subset of YAML, it the most consistent and in-line with the naming
requested by YAML's creators. While it is true that `yml` suffixes have
gained popularity, it is more important to honor the wishes of YAML's
original creators (much like `htm` was always stupid compared to
`html`).

## Other Data Formats

JSON *is* YAML, so that one is covered. This means that `JSON-Schema`
can be used to represent it (including variations in compatible YAML).

TOML, while initially appealing, reveals significant flaws at scale and
does not have the tooling support necessary. 

TSV and CSV are easily represented as YAML. 

Don't even think of suggesting XML.

