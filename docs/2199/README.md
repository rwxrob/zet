# After reading about Anki flashcards realize need standard

As great as Anki cards are, the format for them is unnecessarily complex and non-standardized---especially considering that modern Markdown fully supports LaTeX as well as linked raster images. I think KEG should definitely define a knowledge node type that is easy to use for such things. In fact, all that is needed is the title and the content to make a card. The KEG restriction on title length at 72 runes was removed some time ago allowing more than enough room for the "front" so that the body can be the "back" of the card.

I'm particularly interested in creating zettel entries that are for specific tasks, or "task cards" that have the specific commands to use so that the reference material can be looked up for a given thing. Then the implied query "how do I" can be easily found by putting it into the form of a declarative verb (ex: "List everything in a directory").

If we do this right we can put every little thing that has to be learned into a zettel and create exporters to Anki and other software formats so people can review these things from their phones and the web or just use it as a knowledge base. In fact, we can incorporate this into keg/kn/mim so that collections can be created for flashcard-like study.
