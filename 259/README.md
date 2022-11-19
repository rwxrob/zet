# Use `internal` Dir to Block Unwanted Go Imports

I noticed that the Twitch CLI tool has an `internal` directory at the
root level and it occurred to me that they are doing that to explicitly
proclaim that anyone importing that library as-is is in violation of
their API. This helped me to make a decision about whether to port some
of the `internal` code into my own project, or to just import it as is.
The name said everything I needed to know about that decision. 

Related:

* <https://github.com/twitchdev/twitch-cli>

Tags:

    #golang #coding
