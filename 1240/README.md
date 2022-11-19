# Restream.io, Nice But Unnecessary

Restream doesn't solve any problems I care about.

I had a love affair with <https://restream.io> for all of one week. I
learned the API and everything. I even had real-time messages coming
down from Websocket connections and printing out, all coded in Go. But
the more I realized that I really only need to stream to Twitch, that
there is *nothing* out there that even comes close to usability (from
the perspective of the user) then I got over my Twitch angst and
returned to the fold. I haven't looked at the new API fully yet, but I'm
quite confident there is a direct Websockets layer for events (without
dumb-shit polling like YouTube requires).

Also after I started dual streaming directly to [YouTube] and Twitch with
`nginx-rtmp` container, and managed to get 3 second latency on each, I
never want to add back another laggy middle service again, but I just
don't need it.

[YouTube]: /20210502194445
