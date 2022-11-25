# Dockerfiles, Fat or Skinny, Maybe Both?

I've only been doing Docker container image creation for a month or two
but one of the immediate annoyances is the way having a "fat" Dockerfile
with multiple overlays is much easier to work with during the
development phase because you can make incremental changes and
significant reduce the amount of dev time per iteration, so much, in
fact, that you can just keep using your on-prem registry for it instead
of coming up with other magic. I have to believe (and have heard many
others say) that this is the way to do Docker, that this is as God
intended originally, that it is the very reason overlays are a thing.
But the simple fact remains this produces very fat images with several
overlays.

The other school says you "should never have more than a single `RUN`
and `COPY` in your entire Dockerfile", which is somewhat ridiculous
during development give the amount of time you would sit waiting for
things to update every time. I personally refuse to do this until the
very last stages of a containers development. This makes the end users
of your container not have to download as much, at one time. But if you
make regular changes to your Dockerfile image (as with my workspace
container) then even if you save them half the size your are still
forcing them to download that entire image every fucking time.

It might be possible that "both" is the answer here, fat during
development and light in final form. I did everything to stop from
writing a script to do this very thing, one that would parse all the
Dockerfile and make an intelligent choice about how to combine
everything together. But I'm just not sure.
