# Brilliant BSD developers understand the Rust "safety" lie

Let's face it. BSD developers and their community make the entire Linux community look like kindergarteners with a silly, power-hungry, angry teacher. Before Apache, BSD was the gold-standard of open licenses. In short, BSD has always been wildly superior technology that happened to not get the marketing needed. Everything about it is superior *except* adoption and desktop-like stuff. 

I actually love that the BSD team has always had the good sense not obsess about "BSD on the desktop." They realize (brilliantly) that the desktop is not the target for UNIX-like systems *and never has been*.

Which would you rather have? A community of enterprise networking and hardware people using your project for the most significant components of the Internet and edge computing including Netflix, the gold-standard in streaming CDN architecture? Or, the latest 3d-accelerated desktop widgets and gaming emulation layers? And how about the fact that more computers are running a BSD derivative than any other on the planet (macOS darwin)? In fact, Apple proved that BSD could easily be used for the most superior user-facing desktop experience on the planet. It's just that the BSD team decided to leave that to others.

I have been contemplating using FreeBSD for my base server images---especially now that they have full support for Firecracker hyper-visor. So when I read their latest home page talking about the state of BSD and read the following I wanted to kiss Baldwin on the mouth for being such a brilliant, rational person. Brilliance like this in the face of trends is why BSD is *still* the leading OS for things that have the highest performance, networking, and sustainability requirements.

> Security
>
> Is the FreeBSD team interested in using safer languages like Rust to improve security? Baldwin did not see this as the primary route to more memory safety. "One of the things I work on is a project at Cambridge called CHERI (Capability Hardware Enhanced RISC Instructions) that allow us to push special memory safety into the processor itself, so that you're able to have a much safer version of C itself.
>
> "And that will compose well with languages like Rust. It means we can take the safeness of the language and enforce it further down the stack than we currently can. So my personal bias is I think CHERI is going to be a better solution. FreeBSD is largely written in C and we were able to run the whole base system on CHERI. So we have all of that C code running as a safer C. I think that's the more likely future way to get memory-safe systems."

Managing "memory safety" by forcing code to compile sometimes 100x more slowly has *never* been the solution. It is an ill-conceived band-aide for a problem that has *nothing* to do with the languages that allow direct memory management. Are you going to pull the plug on *all* LLVM language because they are "unsafe"? Fuck no.

Rust will *never* be a language of any particular enterprise scale because it of it's cluster-fuck syntax, horrible concurrency; and *never* good for low-level things because you have to disable safety (while keeping the ridiculously long compilation times). No company that matters with actual benchmarks to hit and budgets to be affected will ever adopt Rust completely. Those that do will fail miserably (as some projects already have).

As soon as CHERI and Risv-V hit the market, in addition to TLS in the kernel in FreeBSD, most applications in that space (that don't require containers) will move to BSD (Netflix always has).

