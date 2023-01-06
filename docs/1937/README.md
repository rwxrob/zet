# Twitch (chat bot) commands as zettels

I've figured out a way to make my life a lot easier when maintaining those useful commands from the Twitch or Discord command line: put them all into their own zettelkasten entries with titles that match the command. Here's the convention:

* Commands begin with exclamation point
* Title starts with one or more commands
* Non-commands are ignored
* First command is main, subsequent are aliases
* First paragraph is under 400 characters [500-maxlen(url)]
* Rest of zet further explanation that can read by clicking link

Command titles will be be one of the priority search rules I'll be adding to KEG/Rat as well:

```peg
Command <- '!' (!(SP / '!') alnum)+
```

This is one of those times when the get-out-of-your-way approach to zettelkasten really pays off. People can make it into what they need because it is so foundational and "paper-compatible".
