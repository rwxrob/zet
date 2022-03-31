# Using ProtoBuf for Twitch Bot App

Just reading that ProtoBuf isn't just for messaging but can be used to
store data to a file. Based on this I'm thinking of making all my chat
logs from the Twitch bot Imma write this way so that when we have
trillions of messages they will parse in the fastest way possible for
searchability and pseudo-database behavior. I'm not adding a fucking
database dependency. That's for sure. Besides, databases for this sort
of thing are way overkill since appending to a file in Linux/UNIX is the
fastest possible IO. It is a disk write, but the memory caching can be
buffered in the app if needed and writes made at the maximum possible
interval. We would only potentially lose the block size of messages if
the application crashed.

* Protocol Buffer Basics: Go \| Protocol Buffers \| Google Developers  
  <https://developers.google.com/protocol-buffers/docs/gotutorial>

    #protobuf #golang #twitch #bot
