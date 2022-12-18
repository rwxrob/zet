# Moving `nodes` TSV to KEG root and adding to formal spec

After looking seriously at SQLite3 for the standard file decided to keep the "paper compatible promise" and drop it. This way people can maintain kegs without needing any specific library. The bloat to add even SQLite3 is just too much.

I'm also dropping the `dex` entirely from the formal spec. It's just a nice convenience anyone can use. In fact, nothing but the following are included formally in the specification:

* `keg` - YAML file identifying keg content
* `nodes` - TSV file in integer order with `id`, `created`, `updated`, and 70 character `title`
* `0/` - (optional) zero node indicating "under construction"
* `<INT>/` - content node with auto-incrementing integer primary key identifiers

To "follow" someone all that is needed is the first line of the `keg` file which contains the mandatory `updated` time stamp. Then, to see exactly what has changed a remote pull of `nodes` is done and effectively `diff`-ed against the last cached copy. KEG apps can then decide which of those changed content nodes to pull, if any.

People can get creative with their titles and use an initial emoji title, but none of that will ever be specified.

Any other meta data besides what is in `nodes` will have to be created and maintained by KEG apps and never be specified --- including tags, categories, links, relations, etc.
