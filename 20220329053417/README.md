# Burned by go.work. Don't Be Me.

Was just informed from my very understanding friend from Twitch
community that I had broken bonzai package because my `z` (and
everything else) was building fine for me because of `go.work`. Moral of
the story: don't use go.work unless you are specifically working on two
things at the same time. Always remove it between coding sessions and
make sure your stuff will build.

Ya know, I knew this would happen, just wasn't used to the new `go.work`
workflow. Now I am. In fact, I've added `go.work` and `go.work.sum` to
all my `.gitignore` and removed them from all my packages. Life is good
again.

I must say, that `go.work` is directly responsible for my proliferation
of package refactoring lately. It makes such things trivial that were a
pain in the arse before. So my relationship with `go.work` continues to
be one of love and appreciation.

    #golang #coding #tips
