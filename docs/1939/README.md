# Length of KEG URL needs to be under 100

While creating [Twitch (chat bot) commands as zettels](../1937) I realized that knowing the approximate size of a KEG URL is important. Twitch limits chat messages to 500 bytes. This means that when creating commands that product output combined with a link that the link needs to be under a predictable size. 100 seems to be reasonable. That is longer than the length of most developer terminal windows.

There are many strategies for shortening URLs, but KEG won't need many of them because the nature of unique integer identifiers already makes the URLs very short and memorable (not unlike XKCD). For example, even with a custom subdomain, the URL to the 1 millionth zettel would be under 30 bytes:

```
https://zet.rwx.gg/1000000
```

Maybe one day I will actually have that many.

That same URL hosted on the free GitHub pages service would be under 40 bytes:

```
https://rwxrob.github.io/zet/1000000/
```

💢 I cannot overstate my joy to have discovered the idea of naming each zet using just an incrementing integer as a universal unique identifier. It has made *all* the difference. So many huge static site generators and blogging engines miss this one simple fact. They are all brain dead.
