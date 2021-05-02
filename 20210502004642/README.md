# ZettelKasten on GitHub

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
  followed by a blank line. Titles are not required, however, and should
  not be over-thought (that is for later when adding to the register).

* Unlike the original method, I've allowed the optionally addition of other
  content, notably a `data.yml` file with structured data in YAML or
  JSON format (keep the `yml` suffix though). Generally, images and
  other assets should go into their own `asset` Zettelkasten (and repo)
  because they usually will be referenced by many other Zettels.

* The main `README.md` file within the top-level of the Git repository
  serves as the Zettelkasten "register" and pulls together all the
  references to Zettels, both locally and remotely in other Kasten
  repos.

* External links out to other content should either be traditional web
  URLs (which can be automatically validated), except when linking to
  another GitHub ZK repo.

*  When linking to another GitHub Zettelkasten on GitHub (or potentially
   other hosting providers that support it) always link to the root,
   never to the specific zettel ID (for example
   <https://github.com/rwxrob/zet>). This allows things to move and
   change as they are supposed to do during Zettelkasten content review.
   (Imagine symlinking or hyperlinking to content you never knew would
   be there later.)

* To get more precision in your outbound links to other ZK repos, you
  can link directly to a search for specific keywords in that
  Zettelkasten repo (for example
  <https://github.com/rwxrob/zet/search?luhmann>). This is more valuable
  to the user of your content anyway because it includes content that
  may be added after you would have made the initial link.
