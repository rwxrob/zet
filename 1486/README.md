# Rust Reality: Nothing Serious At All

Rust and Go have been around for roughly the same amount of time. Yet
nothing serious has been done in Rust. There's a lot of talk and vapor
ware predictions. But nothing *serious* has come from that shitty little
hobby language (preferred by Node developers, with Cargo being ported
from NPM) with the world's worst syntax. When I say serious I'm talking
`Kubernetes`, `Docker`, Linux kernel, OpenGL, TensorFlow, Unreal Engine,
serious. I'm talking, CoreOS, k3os,
basis-of-the-entire-fucking-cloud-native movement serious. Rust has zero
case studies that matter (and a growing number of Ph.d academics writing
papers debunking the lies about "safety" from the Rust script kiddies.
Spoiler alert: to do anything significant you must to with pointers and
throw "safety" out the fucking window when you do).

There's a reason Go has a massive number of significant case studies
published on [go.dev](https://go.dev) and Rust has virtual nothing. But
Rust does have a few. My mind is made up that Rust is dangerous shit
and that everyone should not just avoid, but actively campaign *against*
to counter the flowery lies from its community. (People have written
academic papers for the same purpose. Yeah, it is really that bad.)

Despite my "bias" I've started this zet to keep track of the ones Rust
fans bring up every time I state these uncomfortably objective fact:

* Firefox - right, the org that fired most of its Rust developers
* Alacritty - buggy beta software providing nothing more that others
* Discord - people wised up and don't cite that stupid blog any more
* [Figma] - tiny insignificant company has Rust in prod, big woop
* [Dropbox] - "sync engine" tiny piece, rest all Go (dropped Python for)
* [Firecracker] - interesting, but completely irrelevant, no one uses

Most of these projects have better alternatives written in other
languages. My favorite was when the trendy, inexperienced Discord team
dropped Go for Rust (a bad choice to begin with because they couldn't
code C/C++) and then went to Erlang dropping Rust (which is why people
eventually shut up about their idiotic blog and Reddit post). If you are
making corporate and career mind-share and technical architecture
decisions based on Discord Reddit posts I pity you.

Ironically, all these objective facts about how much Rust sucks just
propel the tiny "community" forward. So be it. Maybe something good will
come of it. For me, it is the fact that I'm actually looking at modern
C++ with a completely new appreciation, and solidified my position on C
as the most important language to learn even if you never code it
professionally. Rust really just doesn't matter.

[Firecracker]: <https://github.com/firecracker-microvm/firecracker>
[Figma]: <https://www.figma.com/blog/rust-in-production-at-figma/>
[Dropbox]: <https://mjtsai.com/blog/2020/03/17/rewriting-dropboxs-sync-engine-in-rust/>
