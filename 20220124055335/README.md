# Consolidating "Learning Labs" into Single Lab

I've come to realize that breaking up all the learning lab activities
and the notes related to them has made finding it again virtually
impossible. Instead, I've decided to consolidate all of the labs into a
single `lab` repo that I can easily search even though it is separate
from my `zet` repo. When I need to document how to execute a task of
some kind (think recipe) I can write that up as a single zettel entry
for easy lookup later and just refer to it consistently from the
README.md files in each subdirectory of that `lab` repo.

The `lab` repo also allows subdivision and better organization of
content. For example, I have a single `nfs` directory or `k8s` directory
under which I can create individual labs on different related topics.
This is also much easier to share with others.

The content of `labs` also will always have the commit history that
demonstrates how each lab grew over time presenting a reference point
for later. Labs will eventually have the completed instructions and code
created along the way, some of which might land in other shareable
projects. 

A single learning `lab` repo will also rise far fewer alarm bells to
anyone evaluating someone for their skill by reading through their git
repos (as opposed to them being flooded with `lab-` repos on all sorts
of topics.
