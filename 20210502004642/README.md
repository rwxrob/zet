# Zettelkasten on GitHub

The ZettelKasten Method is attributed to
[Niklas Luhmann](https://luhmann.surge.sh) who was a very prolific thinker and
writer. The concept is rather intuitive to someone with nothing more
than paper and pen and wooden boxes. It's just a file system that gets
out of your way and lets you think creatively, and then later organizing
those thoughts. Ironically, modern technology has diluted and nearly
destroyed the cognitive value of the original approach. Therefore, my
approach maintains the strict compatibility with the exact same system
on paper. Indeed, I use a notepad with sheets divided in half with a
drawn line to create many of my Zettels before ever (if ever) adding
them to the digital version. Everything I can do digitally I can always
do on paper.

* A Zettel ("slip" as in paper) is contained one or more Kasten
  ("boxes") with a Register (maintained strictly by hand) that ties
  everything together.

* Kasten are implemented as GitHub repos.

* Zettels are implemented as directories within their Kasten repos, each
  uniquely named for the ISO-formatted second in GMT/Zulu time, a unique
  identifier that anyone with a watch can easily create.

* Each Zettel directory contains a `README.md` file that equates to the
  slip of paper containing a minimal amount of text (usually try to keep
  to 25 lines of 72 characters). Limiting the size of a Zettel is
  critically important to the cognitive value of this method.

* Zettels may have a title on the first line beginning with `# ` and
  followed by a blank line. Titles (in my version) are required forcing
  me to think carefully about what this specific zettel will be about.

* Another zettel pseudo-standard I've adopted is to create a video link
  (a zettel cast) on the third line which consists of the television
  emoji, followed by a space, and then a full `http` URL wrapped in
  angle brackets. Zettel casts are simply videos coving the content of
  the written zettel, usually under 10 minutes long.

* Unlike the original method, I've allowed the optional addition of other
  content, notably a `data.yaml` file with structured data in YAML or
  JSON format (keep the `yaml` suffix though). Generally, images and
  other assets should go into their own `asset` Zettelkasten (and repo)
  because they usually will be referenced by many other Zettels.

* I also refrain from linking between zettels preferring instead to
  encourage searching and creation of different outlines that
  effectively compose several zettels together. I learned early on that
  the same failure of hyperlinking as an unsustainable design approach
  (inevitable broken links, for example) exists for the original zettel
  approach. This is made worse by the fact that I create zettels
  constantly and creating the links (although a valuable cognitive
  practice when there is no computer involved) turns out to be a waste
  of time. Perhaps this worked better for Luhmann who never destroyed a
  zettel after adding it to the box, only updated it.

* The main `README.md` file within the top-level of the Git repository
  serves as browsable entry point into the Zettelkasten linking to
  different outlines (akin to Luhmann's register) that are generated
  manually and automatically.

* External links out to other content should either be traditional web
  URLs (which can be automatically validated). Generally, however, all
  links should be explicit such that after a Pandoc conversion to text
  they remain useful (as YouTube video descriptions, for example).

* To get more precision in your outbound links to other ZK repos, you
  can link directly to a search for specific keywords in that
  Zettelkasten repo (for example
  <https://github.com/rwxrob/zet/search?q=luhmann>). This is more valuable
  to the user of your content anyway because it includes content that
  may be added after you would have made the initial link.

* Avoid linking to definitions of any kind since you never know the
  audience. One reader might have to look up every other word, while
  another would be bored and annoyed by all the hyperlinked text. In
  generally, hyperlinking has always been an anti-pattern for knowledge
  consumption. Composable, finite leaf knowledge nodes (our zettels) and
  search parameter optimization in the *user's* control are a much
  better alternative. I call this *search-centric knowledge
  management* and it has become the default knowledge consumption and
  creation method since the first Internet search engine was created.
  Before that we all did it using the TOC and index of the book we were
  reading, because it works.
