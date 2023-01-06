# !rust rwxrob.tv

💢 I hate Rust: the syntax is uglier than Java/C++; it takes *forever* to write anything in it; compilation takes forever; the mod team resigned in disgust over "hypocrisy" of governance board; dissertations have been written about the "lie" of Rust "safety"; CTOs regret it destroying their IT projects; and virtually *no* jobs exist for it. !Go blows Rust away for the things which matter most.

To be fair, Rust and Go can co-exist. They solve very different problems. This is perhaps the biggest misunderstand to which naive beginners fall victim when considering which "serious" language to first learn. Usually you *want* garbage collection, sometimes you don't. Understanding that difference is key to even making a choice for oneself. I do think everyone should *eventually* learn Rust. It will broaden the way you think about coding in general, just never as a first or even second language.

Learning Rust because it "is a good language for WebAssembly" is one of the dumbest things I regularly hear. All the advantages of Rust are completely and totally lost on WebAssembly. Go down the list of advantages people say about what makes Rust amazing and notice that not a single one relates to WebAssembly, which runs in a protected web browser sandbox. Why on Earth would you torture yourself with all that shit? Just use JavaScript or *any* language that is faster to produce code in (Nim comes to mind) over Rust. To me nothing says, "I'm an inexperience noob" more than choosing to learn Rust first and because "it is good for WebAssembly". When you press these people they almost always confess they are actually doing it because Rust is "trending" or some other clueless person (usually a JavaScript script kiddy) told them it was the "cool" language to learn. I call bullshit.

* Using Rust at a Startup, a Cautionary Tale  
  <https://mdwdotla.medium.com/using-rust-at-a-startup-a-cautionary-tale-42ab823d9454>

* Rust Reality YouTube Playlist  
  <https://www.youtube.com/playlist?list=PLrK9UeDMcQLpp9EcYfnoAb4VQvN6931F5>

* Strager concludes not to proceed with Rust, [for now](../1947)

----

Let me tell you a story of the first person who ever told me about Rust.

A person who paid me to mentor them was *hugely* into Rust (mostly because of the active, vibrant, enthusiastic community, at least, the ones who didn't resign in disgust over the hypocrisy of the steering committee). This person had received a psychology degree but could not find a job. That's why they started paying me to help them.

I was open with them about it and let them make their own decisions, as always.

One day they said, "Ya know, I really need to learn Go to get a job. There are zero Rust jobs."

I agreed, but this person had to come to this realization the their own, which was hard.

They learned Go and almost immediately got a job making 100K American dollars a year starting salary specifically because of learning Go, and then they also got to work on Rust there.

Most people learning a language are doing so to become productive and employable, like my friend. Rust distracts you from these goals.

While it is an exciting language for a very specific niche of applications that are yet to be determined, it is a huge fucking waste of time for MOST people reading this.

Like my friend, do yourself (and your family) a favor and master Linux, bash, python, Go, and even JavaScript before even wading into Rust. Then you can waste your time learning Rust if you really want. I don't. I have more productive things to waste it on, like Dota2 or Overwatch.

And, please, for the love of God, learn enough C to understand what all the Rust hype about "garbage collection" and memory management and dangling pointers is even about. Otherwise, you just sound like a sheeple idiot trying to justify your decision to learn Rust first without knowing a damn thing about how software actually works.

***Rust is good for some things.*** Web development is not one of those things. Writing a OS security vulnerability fuzzer? Yes. Want to write device drivers in something besides C? Yes. Want to write a layer between Linux kernel and Java Android API? Yes. Most people, however, absolutely, positively will *never* need to write this kind of software. I prefer languages that empower the most people, not a select few engineers who actually enjoy the shittiest syntax ever conceived and for some reason don't give a shit about compilation times, like, *at all*.
