# Beware of GOPROXY=direct

Like many Go developers who get annoyed really fast by the performance
and time delay to get your modules into the caching servers you might
have something like this in your `.bashrc`:

```bash
export GOPRIVATE="github.com/$GITUSER/*,gitlab.com/$GITUSER/*"
export GOPATH="$HOME/.local/share/go"
export GOBIN="$HOME/.local/bin"
export GOPROXY=direct
export CGO_ENABLED=0
```

This has worked very well for me, for the most part. I mean, `go get -u`
takes an ungodly amount of time, but oh well. But there is something
insidiously wrong with my work habits doing deployment because of this
specifically related to `export GOPROXY=direct`. In fact, I wrote a
whole thing just about the mysterious bug and why `direct` was the main
reason I missed it.

The short version is that my module wasn't getting fully deployed to the
caching servers. They actually care about Go major versioning matching
the import pathing (which I did not fully understand until today). That
means "no cache for you" when it rejects you unceremoniously. You go to
market your amazing creation only to learn that *no one can fucking
install it and they aren't even telling you*. I am so fucking glad that
I tested this on a bare-bones Windows machine that I have configured
like my artist wife were using it. Nothing fancy. I immediately caught
the problem that any other person would be having, and no amount of
CI/CD could have caught it.

So you have a few options:

1. Stop using `GOPROXY=direct` and now that we have `go work` it might
   not be as bad.
2. Always try to install your shit from an simple user machine.
3. Both.

Personally, I'm going to keep `direct` for now because I don't want to
wait forever for the caching servers to catch up.

* [20220414164924](/20220414164924/) Having Windows to Test Go Installs is Heaven
* [20220414164734](/20220414164734/) Go Major Version Path Syncing

    #golang #coding #gotchas #tips
