# Dropping zettelkasten, zet composition, and zet name, back to kn

Originally, my `zet` command was `kn` and stood for "knowledge" or "knowledge node" or "knowledge network." At the time I had never heard of zettelkasten method. I remember bawking at all the people suggesting I just use Obsidian and follow zettelkasten. Then I researched it extensively and noticed a lot of good in what Luhmann did. Now, after using that method for over two years, I can safely conclude that the zettelkasten method is too significantly flawed to be of value in 2023. Don't misunderstand, there are plenty of valuable insights provided, but they need to be incorporated into a modern world, with modern assumptions. Here's a summary:

* Document paradigm is superior to zettel (slip) paradigm
* One section documents (zettels) are still documents
* Paper paradigm is dated and flawed
* Computers are not going away
* Composition doesn't work with documents like software
* Hyperlinking is *still* (and always was) broken
* Knowledge source in MkDocs Markdown is best
* Searchability is top priority
* Search engines and AI are the new normal

These conclusions are fundamentally at odds with beliefs I had about these things before. Like always, I have no problem changing my position on something when presented with new evidence to the contrary. This is one of those times.

## Document paradigm is superior to zettel (slip) paradigm

HTML adopted the idea of a document being the fundamental unit of the WorldWideWeb, and for good reason. The world of information continues to be dominated by documentation in document formats. There's no better evidence of this than the hugely popular and successful readthedocs and MkDocs projects. These projects have very successfully demonstated that when people want something to read, they want it in a consistent, document-oriented, searchable format. In fact, I consider MkDocs with Material to be the defacto standard for all content that has as its priority readable consumption. It is far superior to any wiki content organization, and much more digestable than zettelkasten's disjointed approach to content.

This is no surprise to most rational people. It's how we have been writing school papers, journalism articles, and non-fiction books since the beginning of history. For some reason, I felt the need to overcomplicate the process by breaking them all out and then pasting them back together.

## One section documents (zettels) are still documents

I've been forcing myself to keep my documents to a single section with only a single H1 header at the very beginning. The idea is to keep that idea to the point and independent of others. But, as you can see in this document. This because hugely problematic when a bunch of main ideas go together. Rather than creating a bunch of independent, one-heading markdown documents, I now allow myself to let documents have multiple headings, as expected in a document. This allows the main ideas of the thesis to be presented cohesively within the single document and makes it simple to move those ideas around and supplement them. 

However, just having one main idea in a single document that stands on its own is still valid. 

## Paper paradigm is dated and flawed

I was so wrong about holding myself to design decisions that could be implemented on paper if needed. Many of them I do *not* regret, like the simplification or primary key identifiers to simply incrementing integers over stupid UUIDs. But, on the whole, forcing the overall design to comply with being able to be done on paper is just flawed in 2023.

Luhmann was required to do a lot of silly things because he only had paper. He used dependency linking for example. He had no concept of searchability at all. He was his own search engine who had to read through all his index just to find what he wanted. Such approaches are just, um, stupid today. Computers can not only index every word in milliseconds, but apply complicated AI-generated models to that information. Luhmann would *not* have used paper if he had a Linux computer from 2023. He just wouldn't. He wasn't stupid.

## Computers are not going away

While I still do take notes in an organized way on paper, I almost immediately put those notes into digital format. Why? Because without it I cannot search them. Even in the event of a complete world-ending event, having my knowledge base in Anartica will still be completely unreadable unless all of GitHub is copied over to microfilm or something. Humanities survival will depend on reconstituting our computing power as soon as possible in order to read and use the documents and code saved. This means that humans are already establishing safety measures to ensure computers outlast any just catastrophic event as well. Without them, forget about getting anything at all. So making a basic assumption that computers will *always* be available so long as this knowledge base of mine is a very safe one. And again, Luhmann started zettelkasten before the computer revolution and was stuck using it. Had he started his system in 2023 there is simply *no way* he wouldn't have created a much better system that made thorough use of computers. He wasn't a fool.

## Composition doesn't work with documents like software

When I developed a way for one document to be included into another through composition akin to the same done in software development I was under the naive notion that these messy problems would be addressed like software. But prose is not software. Breaking up ideas into indepenent ones that can be composed back together again artificially imposes complications on the rhetorical style and flow of the final document that are simply incompatible with modern writing. 

What should have been a single document with multiple headings becomes multiple zettels that attempt to stand alone but have to be composed back together. This causes all kinds of headaches when deciding which title to use as the heading, whether to include the verbose heading again or a shortened form of it when composed. And, most importantly, it destroys the flow of ideas and seemless reference to other main ideas rhetorically by reference to "above" or "below" because the chronology of the document is completely unknown to each of the independent document components that are composed back together again.

My attempts at prose composition suffered from one of the same problems as software: dependency management. 

In Go developers will sometimes "vendor" a dependency or copy it directly into the software so as to remove a dependency and level of complexity in managing the source---even if that code is just a cut and paste from a moment in time of another project. This seems inefficient on the surface, but provides huge gains in sustainable project management over time. If the dependency changes, the project is protected from those changes. 

!!! question "But what about security?"

    Sometimes this can be an issue for security since those dependencies are no longer tracked in that way, but by the same token, if a dependency introduces a security flaw it is not authomatically injected into the code that depends on it when that dependency is updated, which is common. So at worst, the risks and reasons to keep the dependency even out.

## Hyperlinking is *still* (and always was) broken

Ironically, Luhamann had this problem with his zettlekasten method. He had to create a system that linked one zettel to another. He even created a way to split an idea over several slips through linking one to the other forcing them to all be pulled in order to read the entire idea. For the time, it was pretty novel. But we can immediately see how silly that is in 2023. 

Hyperlinking is and always will be broken because the reference to the thing might break when the thing goes away or changes. This is why searchability is the top priority. I will maintain separation of documents by using incrementing integers as identifiers, as would be in a proper database, but the thing to link to, or put a better way, to discover, will always be the content itself---particularly the headings of that document.

## Searchability is top priority

I've written about this a ton. Rather than linking to a specifical location in a document or resource that might change it is always better to construct a search query and link to that. This way changes are captured and content is not frozen to that location. It also ensures that any new information on the topic is included in the results as well. For example, say an author has changed their mind on a topic but kept the old document for historical purposes (kind of like me writing this right now). Linking to the search results would pull up results dated more recently with more current ideas on that idea while still including the original content.

## Knowledge source in MkDocs Markdown is best

MkDocs with Material has become the undisputed leader for prosaic writing---particularly technical and educational material. All major software vendors now document their offerings using MkDocs or an almost identical clone of it (usually Hugo trying to be MkDocs, which is very cumbersome). Pandoc is an afterthought at this point. MkDocs can do everything Pandoc does and far more when it comes to getting digestible information out to everyone in a searchable way---including math. A few people will keep with Pandoc for academic writing, but everyone else will vastly outpace them with MkDocs and the many conversion tools to published formats. And let's be honest, this kind of content never belongs on a printed page, ever. It is constantly changing and being updated. The age of *living* documents is upon us and Pandoc was designed to sell overpriced academic books that are overly bombastic, undigestible and proven to force entire universities to buy the latest dead-tree version. That paradigm is as old, crusty, and frankly smelly as the unwashed beards of those who still uphold it.  Be gone with them all.

## Search engines and AI are the new normal

All the AI that is taking over search engines in general needs something to digest to create intelligent results. These tools are being created to digest content in the same way as humans, as coherent documents. Placing a lot of content in disjointed zettelkasten knowledge bases actually works against the future of knowledge management and retrieval. AI is the epitome of searchability. When a completion suggestion pops up while writing that is found by an AI bot if that suggestion includes the document of which is was a part a much more intelligent decision can be made by the AI-assisted writer as to whether to accept the suggestion or not. This also seeds the author with other related ideas from that same document. All the more reason to keep writing as humans always have, as documents.

## Next steps

* I'll be changing all my `zet` references back to `kn`.
* All the composition stuff in `kn` will go away.
* The `keg` content organization is ceasing in favor of intelligent parsing.
* The `kn` tool will be focused on generating MkDocs with Material content.
* The KEGML specification will give way to a rich MkDocs flavored markdown.
