# Revising `keg-index` (`nodes`) file, still no `created`, add children

***Update: Friday, January 6, 2023, 9:51:40AM EST***

Changed `keg-nodes` to `keg-index` since more memorable and not as cryptic for regular creators.

----

After staring at the tab-separated `nodes` file for hours contemplating everything possible that it might ever contain --- since it will be codified and unchangeable after January a couple of things have become more clear when considering the primary reason to have a `nodes` file at all: to communicate succinctly exactly what *is* and what has changed. One cannot know what *is* without knowing what other nodes are aggregated into a node.

***Change in name from `dex/nodes` to `keg-index`*** This simple change solidifies the decision to make `keg-index` a permanently specified format forever. The similarity to `keg` will ensure that the file appears next to the other in directory listings, which seems sensible since there are only two meta-files associated with any keg: `keg` and `keg-index`. The `index` is familiar with those who remember `index.html` and such (but without conflicting). Typically a follower would grab the first line of `keg` YAML file to decide if pulling the `keg-index` file is needed due to an update. But there is no reason to force followers to pull both.

***No creation date needed.*** Since a node is based on an idea, which can change over time, having something that biases the person reading it about how old it is just doesn't make sense. The only reason to have a time stamp at all in the `keg-index` file is to communicate that something has changed. Then, it is up to the KEG apps looking at cached content to compare when more detail is wanted. When and if creation time information is critical (say in a chronological log) then the content itself should contain the time information such as in the `title` or elsewhere within the node `README.md` file. This allows such information to be decoupled from the *actual* creation time as well, say if someone is copying over a journal into their keg.

***Adding children allows cleaner remote syncing.*** At first I thought having every (child) node that is included within a given node was unnecessary since it can be parsed from the content itself and wasn't necessary to a remote follower. But not having that list prevents people from creating follows of specific nodes recursively without a *lot* of extra parsing work. Since the `keg-index` file must already be updated any time any change is made to the node because of the time stamp and potential different title, it is no extra work at all to include a comma-separated list of the integer node ids from all **node include links**, which have aggregation relationship. The parent cannot exist without the children, but the children can exist on their own.

***Still no URLs or hyperlinks in nodes file.*** Other informational links such as URLs and inline terminology and other hyperlinks to other nodes will never be included because the relationship is entirely different and less important. A node with a node include link is not considered to even exist without all of the content under it. This makes including these links in the `keg-index` file essential to provide an adequate overview of what actually exists in any given keg.

***Emphasize use of non-nodes for other content.*** There's no reason to remove `dex/changes.md`, but it is not a node. It is content that lives within a keg but is not formally a part of the keg itself. This intermixing on content is expected and common --- especially when rendering `index.html` content to accompany the rest. Having all actual nodes named with auto-incrementing integers makes it very easy to distinguish the data at a glance.
