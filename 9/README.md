# GitHub API versus CLI `gh` Tool?

At work I have a simple requirement: get a binary Go tool to update
itself and notify the user that it did so when the program terminates,
nothing fancy really. But there are some tough choices to make with
regard to sustainability long term:

* Do we just use a file on a web site someplace?
* Do we use GitHub releases?
* Do we use a custom GitHub API request?
* Do we use the `gh` tool for dealing with GitHub?

I actually finished the whole thing using an isosec identifier in a
file. Simple and universal, provided you have a web server someplace to
put it with your latest binaries. Turns out that we don't, not that is
officially supported anyway, and it would be a one-off that wouldn't be
playing nice with the other software releases and shit all over the
enterprise. After all, we aren't even a software team, we are Kubernetes
High Performance Machine Learning Operations (that's a mouth full).

But we do have GitHub Enterprise and there is where the release is now,
it's just never updated and broken on Mac and Windows, which is why I'm
fixing it. So GitHub Enterprise API here we come.

But hold up a minute, the GitHub Enterprise API (which is the same as
the public but with a different URL and requires token for simple
things) requires something that talks to it. I can't just use `curl`
like before. So do we use `gh` or do we use the Google huge fucking
GitHub API or do we just code the REST interactions for the stuff we
need?

Turns out this is a harder question to answer than I would like. If I
make a `github` Bonzai branch how much of it is direct and how much of
it encapsulates `gh`? Do we bundle `gh` using the Go embedded fs? If I
use an API library where do I store the token? Which kind of token? I
know I can just use my own, or that of our GitHub org, but it feels
dirty doing it. And storing a non-expiring token in a binary just feels
so wrong to me. But we cannot have the user authenticate for this to
GitHub, or can we? Can we assume the user even has GitHub access? If
they do, why not just have them download the release themselves after
authenticating instead of automatically updating?

I think the answer is specific for this case alone, and not something I
would want to do elsewhere. I can embed a token with almost no
permissions, enough to see the latest public release, and then just have
it update without the user ever knowing.

But where is the user going to get it in the first place? They have to
download it from somewhere. That would be the GitHub Enterprise release
location itself. So, do we really want the end user forgetting where
they got this critical application? Do we want to be sure they can still
authenticate to the server? What if they cannot and the embedded token
gives them more permissions than they are allowed? That's the reason for
the Enterprise token in the first place.

What seems like a simple, nice thing to do is actually really flawed. It
breaks an established enterprise business processes and I'm not even
sure if I do it that they would ever be approved. I don't know if I want
to bring it up though because they just want something "that works."
Once again, I'm stuck between the *right* thing, and the "expedient"
thing.

It's this kind of analysis paralysis that shuts me down. I've struggled
with it all my life. And here I am sweating this on Good Friday, like
there isn't other stuff I'd like to do. But I'm, um, feeling the need to
get it done.

    #condundrums #git #github #devops
