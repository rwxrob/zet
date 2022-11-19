# CAVA is Coming Back as CARA

"CARA cares."

Conversational Assistant, Remote Agent is a project I started in 2018
(as CAVA) before I gave up my smart phones. I'm back at smart
phones and conversational interfaces have never been smarter ---
especially on the new Google Tensor chips made for these sort of ML
models. Bonzai is now complete enough to really use, which means we have
conversational command line interfaces as well. And, gRPC and Protobuf
have made possible the fastest client-server data communication the
world has ever known. The time is perfect to create the API for basic
actions and events to happen between CAs and RAs. In fact, I need an
agent to stay connected to Twitch before I do my bot stuff. Rather than
right yet another bot that just talks to one service, I need to abstract
such connections so they can simple be imported (like Bonzai branches)
into an agent and stuff just works.

I'm thinking I could even make the agent able to read the same `vars`
and `conf` as Bonzai, actually, for that we need to add a `var listen`
that turns on an encrypted (mTLS gRPC Protobuf) listener that just
changes values turning the local cache into simple, remote, database.
We'd have to do the same thing with `conf listen` but in all or nothing
edits of the file, we'd send the entire YAML file for editing, with a
time stamp, then accept the entire buffer to overwrite if not already
updated.

The first iteration of all of this will be just a agent with the ability
to accept plugins, compiled in or otherwise. Most of the heavy
conversational stuff will be in the mobile phone itself. The app is just
a light weight, PWA that takes voice input and sends it directly to the
remote agent without alteration. The agent will be where all the ML is.
If it doesn't understand, he can immediately response. I mean, we are
talking about one agent (microservice) dedicated entirely to a single
voice interaction with a single end user. There will be zero latency
this way., he can immediately response. I mean, we are talking about one
agent (microservice) dedicated entirely to a single voice interaction
with a single end user. There will be zero latency this way. 

This reminds me that we need to build ML into Bonzai command line (Seek)
parsing so that it can correctly guess the closest possibilities rather
than be so strict about words and spaces and such. In fact, I want to
make Bonzai eventually able to take a regular expression as a field
instead of what we have now.

    #cara #cui #assistants
