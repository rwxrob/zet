# What is the Best Way to Learn Go?

The hard way, of course.

> 🤬
> You do not need to spent any money whatsoever to learn Go programming.
> There's nothing magical about paying that is going to remove you from
> the responsibility to learn it just like anyone would *without*
> paying. If you have cash to burn, great, support an author or content
> creator. If not, don't panic.

I learned Go after having learned several other languages already. So
when I did the *Tour of Go* it was annoying, but I got it. Eventually,
I have up on it as a waste of time and just jumped in to create
a project.

My first Go project was a password management utility for SKILSTAK to
help me help young community members remember their passwords. When
I needed something, I searched it and added it. 

> 💬
> When I discovered PGP/GPG was in the *standard* library I immediately
> fell in love. Only people in the security space will understand why
> that is such a big deal.

Your learning path will probably be very different than mine or others.
Choose your own path. Here's what I recommend having helped 100s at this
point to learn it (and get jobs coding it).

> ⚠️
> Make sure to read the *actual* documentation before anything else on
> the Internetz.

1. *First learn the Linux command line and bash.* This is a very
   unpopular recommendation, but Imma make it anyway. There are many
   people who do not use Linux to code Go (which is part of its appeal),
   but those who do will always have several advantages over them. Take
   the time to learn Linux, containers, `vim`, `tmux`, and `lynx` or
   `w3m` and how to script in `bash` (at least) before jumping into Go.
   Besides, you'll be that much closer to learning C, which I could
   argue *requires* the command line for development. You might even
   learn C *before* learning Go. C is certainly not more difficult than
   Go, it just misses many things Go provides (and is the reason Go was
   created at Google in the first place).

2. *Learn any other language first.* As easy as Go is to learn, Go is
   not for people who have never coded anything. Your first language
   really doesn't matter. I recommend something simple and imperative
   (like `bash` with `shellcheck`). The creators of Go would definitely
   recommend learning C as a first language (since they helped create
   it). In fact, the official tag-line for Go is "a simpler C." 

3. *Get familiar with Go basics.* This is probably the hardest part
   because Go is undergoing changes that affect beginners, mostly
   modules and things like `ioutil` deprecation. *All* the
   'beginner' existing contend is *very* out of date. The best I can
   recommend (until and if I complete my own beginner content) is *Tour
   of Go*, which assumes you have some programming experience. While
   I really like the *Head First* series of books from O'Reilly,
   I cannot recommend *Head First Go* at the moment. Jay is a great
   author, but the content is very out of date. Perhaps you can find
   something useful on <https://golangresources.com> but probably not,
   almost all of it is out of date or just stupid.

4. *Read 'How to Write Go Code'.* This is a critical read because it
   covers the idiomatic things that aren't strictly required but
   preferred in almost all Go code. This has many examples of Go that
   will help make it seem familiar --- especially if you aren't used to
   the reverse notation of type specification and such.

5. *Read 'Effective Go'.* Even though this was written a long time ago
   it is really a must read still even today. 

6. *Read the Go language specification.* If reading the language
   specification doesn't appeal to you, then you might not actually be
   that interesting in coding in general. In my experience, the best
   developers are attracted to specifications naturally. Understanding
   the specification will mean learning EBNF (learn ABNF and BNF while
   you are at it). Specifications are written in these meta languages.
   (You could learn PEGN.dev as well.)

7. *Read and write Go code.* Get a GitHub account and identify some
   solid, simple, Go code bases and read them. Search the Internetz for
   `golang` (the official search term for Go). You might start with Go
   itself. The standard library is very well written. Some others that
   seem good are the `gh` GitHub tool, Docker, Kubernetes, Helm. I have
   some Go code you can look at as well.

Related:

* How to Write Go Code  
  <https://golang.org/doc/code.html>
* Effective Go  
  <https://golang.org/doc/effective_go.html>
* Go Specification  
  <https://golang.org/ref/spec>

Tags:

    #faq #golang #coding #learning #100daysofcode
