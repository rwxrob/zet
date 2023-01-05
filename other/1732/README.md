# Looks like `errgroup` is the thing to use for concurrency

Been a while since I checked in with tunable worker pools and it appears `errgroup` is the thing to use in this new `context.Context` world. I couldn't find my own worker pool abstraction that I did some years ago, but probably just as well. Anything without `Context` these days is really, um, bad. I did find neilotoole/errgroup[^1] which is a nice implementation that includes being able to throttle up and down the number of concurrent jobs in the group.

I won't really need this until I get the other framework for `keg grep` done, which I can do in a linear way for now and layer in the `errgroup` later.

[^1]: <https://github.com.com/neilotoole/errgroup>
