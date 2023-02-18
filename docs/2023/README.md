# Which protocol? net/rpc, gRPC, WebSockets, or REST?

> "Can I get away with net/rpc? Or, do I really need gRPC? Or, do a use a slower JSON-based protocol (like WebSockets)?"

net/rpc forces ugly method signatures and requires everything be written in Go.

gRPC has a lot of support, but is very rigid in its declaration of messages and requires re-compiling every change to the structure. You cannot just add another key-value pair.

REST is fast, but there is no promise that each individual HTTP request won't force a new HTTP connection. Most modern web browsers and technologies do support keep-alive by default, but that is not specified by REST at all.

WebSockets is basically an established TCP/IP direct connection to any server that has a web front-end that supports WebSockets. Once established, the connection is guaranteed. WebSockets is the industry standard for concurrent web-based gaming (agar.io, etc.)

OBS uses WebSockets for everything so that anything can talk to it in any language and there are lots of libraries for it. WebSockets is really fast enough for most modern applications. WebSockets is already designed to be event-based as well. And many existing services already use WebSockets. Restream, for example, uses a WebSockets design to rebroadcast the stream of real-time chat coming from very intense streaming chat sources. Web developers already know WebSockets, so there is another advantage when encouraging people to make and maintain plugins for your framework.

There are a lot of exciting replacements planned for WebSockets, but in this case, I *want* the old (mature) solution. It has more support, more people can code it, and there's a lot more that will return in a search request about it.
