# Server-side includes and templates are the wrong fix to problem

Adding footers and header to web pages has plagued devs since the beginning, but the solution is *not* to complicate the source content with a template system. Instead, simplify the *content* and wrap it into something that presents that content in expected ways, in other words, apply fifth normal form (or something like it) to your web content *before* trying to serve it up to anyone. Then you can semantically deconstruct the content and present it without having to clutter the content itself up with template syntax and plugins.

Does this mean that you must have a database for a web site?

No.

You just have to use a consistent form for your content and create types of content *in advance*. Then you can reliably parse and present that content in whatever view is required, including Web. This was the basis of my original Hugo data-centric tutorial.

* <https://github.com/rwxrob/hugo-tutorial-link-data-to-type>

The challenge is that people by nature do not like to organize anything. The Web is the result. So, to combat the impossible complexity of getting humans to act in a reliable, organized way, we can create an organic, messy way of meshing content development with how the human brain works: zettelkasten. These "mind maps" allow people to be messy, but allow us to create at least a base content type for representing in rough form, then later, we can create other more sophisticated types from those types. That way humans only have to feel constrained in one way: one main thought per zettel. This is the sort of thing that would occur naturally when just saying to one's significant other, "Hey, did you know ...". That thought usually ends as soon as it is expressed, same for a zettel.

But here's the greatest challenge: getting enterprise to accept these realities and embrace them. These bloated idiotic companies are more willing to pay millions of dollars for "taxonomies" and data systems, and ungodly categorization systems that no one ever uses then to allow all their corporate data to be messy and organic. So long as you have a powerful search engine into that mess, you are fine. But corporations *do not* believe this, and likely never will. If and when I ever get a chance to convince them of this it will be to sell them Mim (my keg/zet at the corporate level).
