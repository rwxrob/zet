# When Bonzai Names Collide

Now that everything is going in the root module for Bonzai, so that
`foo.Cmd` is the main thing, there comes a moment when exported command
names may conflict with sensible high-level functions. Such was the case
with my `rwxrob/uniq` branch. I have `Hex` and `UUID` but I also had
`Cmd` variable with those same names because I want people to be able to
important any of those Bonzai leaf commands all by themselves. The
answer is just to add `Cmd` to the end in those cases because the Bonzai
stuff is more specific. So `uniq.HexCmd` would be the thing that gets
imported, and `uniq.Hex()` is the high-level function anyone can call,
Bonzai or not.

* https://github.com/rwxrob/uniq

    #golang #bonzai #coding #tips #naming
