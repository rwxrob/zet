# Monorepos Do Make a Lot of Sense for Enterprise

Working with some stuff for work and realizing how totally different a
monorepo approach is to their applications. Here's why.

* **All vendor code is frozen on inclusion.**

  No sane company would ever leave itself vulnerable to the whims of
  FOSS developers these days. This means downloading and vetting a copy
  of *all* of the code and ensuring it is Apache-2.0 (or equivalent). A
  company can be grateful and benefit from FOSS contributions, but you
  can be damn sure they are going to vet an "vendor" any of the code
  that goes into any or their flagship internal and public-facing users.
  What if a developer just deletes the repo? One `go get -u` and you are
  fucked because you have lost the only copy of the code that you depend
  on. Companies that don't "vendor" their dependencies are just fucking
  morons waiting to be owned by some script-kiddy's political whims.

* **Versions don't matter as much.**

  Once vendor dependencies have had frozen copies of a specific version
  keeping up with the versions matters very little. In fact, there's
  very little reason to ever update those vendored versions unless a
  security report is advanced. Companies with any sense will be doing
  their own regular security vetting of their code bases anyway instead
  of trusting the Internet to keep them safe.

* **Single "product" for internal consumption.**

  Internal developers are going to look at the entire API as a version
  (much like an entire language) rather than the granular versions of
  each and every subpackage.

I'm happy to report that Bonzai plays very nicely into all of this. Even
though Bonzai branches are their own repos, the code in them is *very*
modular and easily to add to a monorepo with little effort during the
vendoring process. I know because I just completed doing that very
thing).

    #golang #monorepos #coding
