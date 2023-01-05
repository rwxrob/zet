# Test Bonzai Standalone Branches for Z.Conf Dep

I added `UseConf` and `UseVars` and just tried to test my `twitch`
branch as a standalone and realized that because it wasn't composed into
my `z` branch that it doesn't have a `Z.Conf` set. It's an easy fix, but
I just have to remember to test the standalone versions more thoroughly.
It's hard to test them, because they have to be compiled and then every
scenario tested against the binary. I feel a `bon test` suite of
commands coming to do exactly that. There's no better testing than
against the compiled binary itself.

    #golang #coding #bonzai #gotchas
