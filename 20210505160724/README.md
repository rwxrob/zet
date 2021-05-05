# Searchable ISOSEC Unique Identifier on YouTube

I've fallen into the most sustainable solution for looking up videos
reliably in YouTube, and it's not by using their unique identifier. If
you provide an `[<isosec>]` identifier in your title you are free and
clear to do whatever organization you want. You have no dependency on
any YouTube API calls or integration. Just pass a query to the specific
channel for that identifier and it is guaranteed to find it.

```
https://www.youtube.com/c/rwxrob/search?query=20210505160724
```

The most valuable part of this approach is that you know the unique
identifier *before* you do everything with it and post it. That means
you can set it to the same thing as something else, in this case another
zet with the same identifier stored on GitHub with the current
description. Then that description can be synced automatically and
rather simply with an API call any time you update the written
description. You control your descriptions in your GitHub instead of
editing them on YouTube and trusting their editor. You can also add
trailer sponsors and link information to the description. If you are
using Twitch this means you can completely ignore the descriptions when
highlighting, export everything, and then update all the descriptions of
*both* Twitch and YouTube in one shot having composed them in your
favorite local editor.
