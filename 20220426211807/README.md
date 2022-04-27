# Mim KEG Master Knowledge Node (Mono Repo)

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
containing the same information. GPG and Web rendering are *progressive*
additions of technology where available, not dependencies.

    KEG/
      updates            - lastmod(isosec), path, titles
    README.md
    README.md.sig        - optional GPG signature
    index.html           - always ephemeral and rendered from README.md
    assets/              - reserved for Web content, but still a KN
      README.md
      README.md.sig
      main.js
      main.css
    zet/
      20220426213407/    - KN Type: Zettel, isosec unique identifier
        README.md
        README.md.sig
        index.html       - rendered, ephemeral
    lab/
      20220426213452/    - KN Type: Lab
        README.md
        README.md.sig
        index.html
        foo.go
        go.mod
    info/
      README.md
      README.md.sig
      index.html
      hacker/
        README.md
        README.md.sig
        index.html
      job/
        README.md
        README.md.sig
        index.html
    cv/                  - KN Type: CV
      README.md          - partially generated from data.yaml
      README.md.sig
      index.html         - generated from README.md and gen.go
      data.yaml          - main file
      gen.go             - generator
    foo/                 - anything needing short url, generated
      README.md          - standard KN node file
      README.md.sig
      README.gotmpl      - (extra but allowed)
      index.html
      data.yaml          - standard KN node file
      data.yaml.sig
      gen.go             - anything with gen triggers generation
    articles/            - KN Type: Article
      README.md
      README.md.sig

The Web rendering being intermixed is an inconvenient requirement given
the world's dependency on the WorldWideWeb right now. This way, if
anyone wants the source, they can just add README.md to the end or
README.md.sig to see the authorized signer.

    #mim #keg #structure #design
