# "Go is a glue language" (Taniwha3)

Taniwha3 spewing bite-sized nuggets of dispassionate wisdom again. God I love that person.

Go is there mostly used to replace Bash, Python, Perl, Ruby, Node, and Java. These languages have made names for themselves by being fast to develop in and relatively fast to execute with optimizations being available when needed. But are these also glue languages?

I would suggest that for most use in the enterprise and beyond, those languages are primarily used to glue together other services and functionality within those organizations. A case could be made that "microservices" are just glue. In that sense, maybe "glue" includes middleware.

Kris Nova has stated that "most of us will be coding in Go for our lifetimes since Go is the main language for middleware"[^1] (but expressed strong "hope" in Rust for the future of distributed systems wanting to influence its consideration).

I agree with Kris completely on this. Go fits *above* the space that Rust seems best to me:

* Integrations with LXC (docker should probably have been written in Rust)
* Virtualisation (like Firecracker[^2])
* OS development (like gamozo does for fuzzing)

Go has no real place near in that same space (although people have tried) as well as most[^3] things written in C. Go fits *above* such things "gluing" other systems together. Rust is likely better at integrating into the kernel, but not the kernel itself (which Torvalds has publicly said will "never be anything but C").

In fact, just having a compiled monolith in my `z` command makes getting productive on anything much easier than with a bunch of scripts in any of those language --- all of which require the installation of an interpreter.

[^1]: Paraphrasing from a tweet that has since been deleted from move to Mastodon.
[^2]: "Secure and fast microVMs for serverless computing." https://github.com/firecracker-microvm/firecracker
[^3]: Gerrand, Andrew. "C? Go? Cgo! - The Go Programming Language" (2022, Mar 17). *go.dev* https://go.dev/blog/cgo
[^4]: Vaughan-Nichols, Stephen. "Linus Torvalds prepares to move the Linux kernel to modern" (2022, Feb 25). *ZDNET*. https://www.zdnet.com/article/linus-torvalds-prepares-to-move-the-linux-kernel-to-modern-c/

