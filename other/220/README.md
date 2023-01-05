# CARA Network Protocol

Decided to leverage the most widely available network protocol in the
world instead of create one that might be significantly faster but
unable to piggy-back on top of existing ones. Websockets over TLS with
HTTP is the fastest. There's also the most code written for it and it
has the most support in the standard libraries of all languages.
Protobuf over gRPC support in JavaScript (for example) is probably
spotty. This would also mean that remote agents could be deployed in web
assembly. From an operations perspective this is fine since I can create
remote agents that take over web servers and broker the traffic in
undetectable ways. People will think they are hitting the web server,
when in fact, they will be accessing my remote agent that passes the
HTTP requests and traffic on to the actual server. Being able to deploy
a man-in-the-middle attack with a remote agent is a nice secondary
benefit of using established protocols, often with weak security.
This means that an remote agent will just be another web server like all
the others. This also means that all the RA code will double as
microservices code. The main design decisions after that are on what
form of communication we should do. I think we should have stateful
(REST-like) API requests that use the traditional POST form encoding and
also have a secondary protocol for web sockets. The agent will pass
communications between different responders through Go channels of byte
slices to keep the overhead distributed across the different responder
goroutines. Sounds like net/http is going to be enough for all of it.

* On concurrency in Go HTTP servers - Eli Bendersky\'s website  
  https://eli.thegreenplace.net/2019/on-concurrency-in-go-http-servers/
