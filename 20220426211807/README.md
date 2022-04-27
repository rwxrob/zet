# KEG Master Node (KEG Site), Early Spec Thoughts

So often I need to link to a very small bit of code to convey how
something is done. I would put them in an *info node* if I could include
code, but nothing that supports info nodes also supports code snippets.
This means we need something sustainable that is tied to it. I believe
the solution is a good 'ol *knowledge node* with code in it. A zettel is
going to be too limiting to contain all the stuff in the lab ---
especially if I write it as a process of steps to follow and use more
than is allowed in ZettelMark. This is more than just a zettel. A
knowledge node is designed for public consumption and less about just
brainstorming. So in `mim` (the knowledge management monolith that will
contain `zet` and `live` and `kn` and `keg`) it would be within the same
knowledge monorepo (if even a repo at all). I'm thinking it could be a
separate top-level branch called `lab` in which code experimentation
goes.

This particular example has all the bells and whistles included. Some
people won't necessarily want to render everything for Web ---
especially when other followers have `mim keg` from the command line to
use to read anything on KEG in their terminal (or GUI eventually)
without any web rendering at all. In principle, everything here that
takes a computer to create could be replaced with just folders of paper
containing the same information. GPG signing is a *progressive*
additions of technology where available, not dependencies.

    KEG/
      manifest           - sorted by lastmod(isosec), path
      sigs               - GPG signatures by path, one per line
      follow             - list of KEG URLs followed
      cancel             - cancelled KEG URLs to ignore completely
      types/
        infotag/
          README.md
        zettel/
          README.md
        lab/
          README.md
        cv/
          README.md
        post/
          README.md
    README.md
    zet/
      K20220426213407/    - KN Type: Zettel, isosec unique identifier
        README.md
    lab/
      K20220426213452/    - KN Type: Lab
        README.md
        foo.go
        go.mod
    info/
      README.md          - KN Type: InfoTags, multiple h1 tags, <380 each
    cv/                  - KN Type: CV
      README.md          - partially generated from data.yaml
      data.yaml          - main file
      gen.go             - generator
    foo/                 - anything needing short url, generated
      README.md          - standard KN node file
      README.gotmpl      - (extra but allowed)
      data.yaml          - standard KN node file
      gen.go             - anything with gen triggers generation
    posts/               - KN Type: Post (edited for publication)
      README.md

Note that *no Web code of any kind is allowed in any KEG node* (unless,
of course, the content itself is *about* Web development). This is by
design. Web pages are one form to which KEG Markdown may be rendered,
but rendering is out of scope for the KEG project.

However, someone may want rendered Web pages *next to* a KEG site, say
if both are in the same GitHub repo. Since KEG does not fundamentally
depend on Git it could still be saved there for convenience. The same
goes for hosting on a web server. For example, I could have `rwx.gg`
pointing to my rendered web pages while `keg.rwx.gg` points to the raw
KEG data being served over HTTP, FTP, Gopher, or Secure Shell (`scp`,
`rsync`, since nothing about KEG cares about the transport protocol). A
KEG node is just another static site to be mirrored, that's it.

One fundamental different this separation has from previous designs is
that there is no longer an optional `index.html` that lives next to the
`README.md` file bloating up the entire KEG node.

    #mim #keg #structure #design
