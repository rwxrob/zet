# SKILSTAK Beginner Boost Info Commands

Going to try something new this year. I'm going to attempt to write all
the written content as consumable *info commands*. This is a variation
on the interactive story adventure idea I had earlier. The writing
process will follow the same graph model. I'll start with a title that
has info commands. Then I'll write out the first info command, with it's
own info commands, and so on. Since we removed the end date of the Boost
I don't care if it goes really long. I'll shoot for wrapping in
mid-August, but we'll just go with it.

1. !Welcome, !friend.
1. !Learn Like a !Hacker
1. !Setup a !Home !Lab
1. Learn !Linux !Terminal
1. !Develop !Tools in !Bash and !Go
1. !Meet, !Communicate, and !Publish
1. Get and Keep a !Job

The above version is a bit distracting at the moment because it has all
the command bangs showing the hot words, but I'm going to drop them from
the documentation and let people guess at the significant words in the
title. Eventually, I'll have info commands for every significant word in
the entire thing. I want to drop the messy use of bang prefixes
eventually because pretty much every word in the sentence would have to
have a bang in front of it at that point. Then we can just add shortcuts
for long words (ex: !kubernetes -> !k8s).

I've already got the word parser for that. I prepared that for KEG. So I
can create a tool that will audit all the words used. Then I can create
lexicons of significant and insignificant words and have the `rwxbot`
try its best to answer anything that begins with a bang or ends with a
question mark. That's the holy fucking grail. Imma make it.

* [20220426141705](/20220426141705/) "Info Commands" is What I am Calling Them
* [20220426142235](/20220426142235/) Writing a Book with Info Commands

    #edtech #boost #infocmds
