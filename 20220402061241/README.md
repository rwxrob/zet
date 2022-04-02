# Realizing `vic` in Bonzai Challenge

The `vic` tool that I use all the time just calls `vi $(which $1)`. But
there is a lot of functionality in that little command. This means
ultimately I will be porting core commands like `which` into Bonzai
commands, which makes sense if I'm ever going to get a truly
system-independent monolith. In fact, I'll end up porting all of the
main UNIX/Linux commands over eventually, all with Bonzai equivalents
that don't use getopt at all. At that point, strangely enough, people
will be able to write Bonzai shell scripts in addition to using it as a
rudimentary shell almost identical in design goals as BusyBox, the core
multicall binary of Alpine. One day this will be a thing. All the
foundations are there to make it happen. Basically Bonzai shell is just
a Bonzai multicall binary AND monolith (so people can set their shell to
`z`, or whatever) except for the requirement to compile in new commands
instead of adding yet another shell script someplace. In other words,
imagine if bash allowed anyone to extend the builtin keywords, syntax,
and commands by just compiling their own copy. Compiling bash is such a
pain in the ass that would NEVER be something anyone would want, but in
Go --- with its hyper-focus on compilation efficiency --- it is a
no-brainer. This is why Pike and the gang focused so heavily on
developer efficiency and simplicity. Considering replacing shell scripts
with Rust is fucking laughable, as would be C, but it is completely
rational and doable in Go.
