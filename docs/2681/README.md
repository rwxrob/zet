# LOG20240908080729: Sunday, September  8, 2024,  8:07:29AM EDT

Looks like I need a Twitch bot of my own to set all the tags and stuff the way I like them. Not sure if the API even supports it, but we'll see.

Pretty sure I'm going to do most of my livestreaming of coding and stuff from this Macbook Pro laptop 14" so I have to setup some of the streaming things first. Might as well do that right now.

I did notice that chat messages can how be sent to the channel without a full IRC client, so that's cool.

My wife is doing "the Elane" in front of me. There is no music.

We have a better plan for what is going into my "studio" since I do most of my stuff from the laptop lately and love the flexibility and ergonomics of the laptop way more than being chained to a desk with a chair. In short, all the coding and random streams will be from this laptop, period. The only thing streamed from my "desk" will be my Zwift cycling streams. In fact, that "studio" really isn't a studio, it's more like a gym/workout room now. Nothing in there but my indoor bike setup at the table with fans, and the yoga mat on the ground. I can code in there, but it will be from the laptop. This means I can code outside, like now, as well and people won't even know. I'm never doxing anything about our location, which my wife loves. Hell, I can even make coffee while streaming and not even dox anything.

I cannot stand these Bluetooth headphones. They have the shittiest sound quality. Also, Doris says, "They say you can have all kinds of issues with long-term headphones if you don't use wired headphones." Where are they? (Headed to the car to check for my Altec-Lansings.) OMG! These are so phenomenally better. Time to write some code.

Wondering what is the best bot account approach. I have done stuff with my own PAT before and it works fine. Just don't want to code with that while streaming because I am prone to doxing it too easily.

Ya know, I just realized I could go back to leaving the coworking music stream on all day again since I can just lug around the laptop wherever I am, even when I'm coding on my other main work laptop. I wonder. Just got the idea because I want to do something from another secure computer that isn't being streamed and that could be my work computer in this case. This means that anytime I want to test something out on my server lab VM host that I could do that on this stream. I have to figure out how to record streams from this laptop as well so I can do the shorts.

Need to create a calendar with the music for the day so people can tune into the music they prefer. Also, I will never be playing DJ on any of these, absolutely nothing but music so as to never miss out on anything or have that annoying talky DJ factor. I can do talking streams that are focused on some topic when there is talk. Also, nothing but bangers in my playlists, stuff that I absolutely adore.

OBS is *so* buggy. Wasted 40 minutes just setting up a privacy screen.

I started a project for livestreamer community management some time ago. Need to find all that stuff.

Found it! I called is `cozy` (as in "cozy communities" or that thing that goes under your coffee cup to keep your wife from yelling at you for ruining the furniture). In fact, I had a whole repo created and summary design and I completely and totally forgot I ever did any of that. I'm getting *really* old. Cozy is the larger framework for community collaboration and kind of encapsulates the `live` command I was working on before. The `live` app was a universal tool for making a livestreamer's life easier, including from the command line. Found `live` as well. I had a good start on the domain model. But looking over it just need to get some business logic encapsulated into high-level functions and start using them however.

Woah, Twitch has an entire helper CLI application now, written in Go, of course. https://github.com/twitchdev/twitch-cli This means there is very little need to do much of anything extra. Makes me want to code everything in bash again.

And another thing, this is a `brew` cask that has its own git repo. There's something really cool about this as a method of distribution for casks. I'm getting a little turned on. This is why so many developers are just using Macs these days. Linux purists can fuck right off. This shit is so drop-dead easy and elegant and the bulk of gainfully employed programmers out there are probably using Macs (including Rob Pike and Ken Thompson). After all, Mac is BSD (which is far and away a superior operating system to Linux).

The Twitch API team has really stepped up their game. The `twitch-cli` is a thing of beauty, even using `goreleaser` (like all our stuff at work that I recently implemented). In fact, their configuration file looks like it gets around the limitations of Go when using "innersource" model repos on GitHub cloud portal (as opposed to enterprise server). These hooks are really intriguing:

```yaml
before:
  hooks:
    - sh -c "go env -w GOPROXY=direct"
    - go mod download
```

