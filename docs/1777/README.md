# KEG indexes over tags

Tagging serves no purpose unless a collection with those tags is available for query later. So rather than add tags to a **content node** it is better to add the node to an index for the given tag. It's then trivial to search the tags indexes and create a relational index that has a list of all the tags for a given content node. This also maintains the could-be-done-by-hand principle of KEG design.
