# Idea for collaborative pomo/coworking REST API

The idea of coworking is exploding on the Internet. More and more people are working together without necessarily going into any office---or even any coworking space. They are simply working together, usually for entirely different companies, doing entirely different things, but sharing that time with others in an informal way as if virtually sitting next to them in the same coffee shop, park, or beach front. It's something I learned about on Twitch and have come to really appreciate myself. It gives all the benefit of a "water cooler" with the freedom to pick which group of people you want to bump into, learn from, and get to know.

By the way, this isn't the first time people have done this. UNIX started it with commands like `ntalk`, `finger`, `screen` and the `.project` and `.plan` files back with UNIX was associated automatically with multi-user systems with literally thousands of concurrent users. If a user wasn't on the system they were likely in IRC and could be easily reached. Everyone felt like they were close to one another and connected because they could literally see the processes that others were running, and if given permission, even look into the files they are creating. They could even share a keyboard with one `screen` session startup. In fact, the modern coworking movement has a lot to learn from just how powerful that entire framework and community was all that time. The secret was in the forced homogeny of the system. There was only one system that allowed it, so *everyone* was there.

Obviously this has me thinking of what a modern version of such an service would look like. Clearly no one is going to share the same system, but the world of micro services and APIs has gotten so large that it is time to rethink what such a collection of services would look like and how to deploy it.

* `ping` - get a real-time status about a person, their mood, are they online, busy, etc.
* `todo` - public todo list with progress and percentages
* `pomo` - where a person (or community) is in current focus and upcoming break
* `work` - current project summary of what a person is actively working on
* `mood` - what is the person's current mood, this is popular on GitHub as well
* `week` - upcoming public calendar for the coming week (only), optionally recurring
* `note` - send a short offline note someone (or oneself), with delivery date
* `post` - post a temporary micro-blog message including links to other longer posts
* `time` - start one of several personal timers
* `poke` - setup an alert for oneself sort of like an alarm at a given time, possibly recurring

## How could be implement this?

My first thought is that we could define a main server API implemented in REST to enable the most integration possibilities. Protobuf and gRPC would be nice, but overkill for this. Keeping things as simple as possible would allow scripts to be thrown together with `curl` that provide the POC work for other, larger applications to follow. Server maintainers could decide which services they wish to provide. In fact, stuff like Mastodon would just be another service and not the entire focus of the server. Micro-blogging has always just been a tiny part of the original coworking UNIX framework. Here are some other services that would be needed:

## Post could cover git commits

The `post` command would be to post everything and support tagging (like any other) and people following others could filter the posts that they only want to see. The person doing the posting should be free to post as much as they want without fear of overwhelming those following them. This is a very big flaw in Twitter, Mastodon and any other micro-blogging platform that has no consumer/follower filter capability (and it is really such a no-brainer to add). We don't need "classes of notifications" just the ability to reliably filter by regular expression and a social contract to use certain community hashtags for whatever.

## What about blogging or Zettelkasten?

There wouldn't be a need for a `blog` service because there are so many different ways that people want to host their blog. The `post` would be enough to inform everyone that you have something to look like elsewhere. The `post` message size would be finite and the message itself guaranteed to self-destruct within a given time period to avoid the horrible problem of content rot on Twitter or any other platform. This creates a finite amount of data stored on the system for any specific user that could even be easily managed with a simple flat-file database. In fact, the database backing the service would itself be an API to which people could attach different storage methods.

## Doesn't Discord do this?

People try to use Discord for this stuff, but let's face it, Discord has all the control and isn't giving any of it up. It is much more powerful to integrate an open system with Discord than build the entire thing upon a very closed system. Discord is there to make money, not promote actual value between people. The people and communities *are* the product on Discord and that is where their legitimate connection to human beings ends: profit.

The same is true for Twitch. Twitch wants to promote more time on their service and does not really care in the end about promoting connections between people who consume their service. It's not bad. They are a company like any other driven by profit. And while it is profitable to promote a sense of community on their platform, it isn't always in their best interest to promote individual development. Otherwise, they would promote more educational streaming and direct community building connections. But they don't. They can give it all the lip-service they can give and still never be authentically interested in any single person who uses their service. They don't give a *shit* about the people there if they don't bring in money, and why should they.
