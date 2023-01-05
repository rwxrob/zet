# Lobste.rs Reminds Me I Need a Site

Just hosting my Zet on GitHub isn't going to cut it. I always knew that but couldn't get to creating the static site generation part of it.
Mostly, because I needed all the pieces with which to build it: PEGN and
Bonzai and `zet` mostly. Well, Bonzai is about done. PEGN specification is done,
but I need to create a new `pegn` Bonzai branch now that handles and
deals with PEGN files and the AST. But before that I need to port all
1122 lines of `zet` bash into Go code, with all the libraries well
factored out of it as I go. That is going to take a while.
