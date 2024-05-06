# Use GitHub App tokens for Go private builds?

No. Despite how many people keep recommending to use a GH App token to create CI/CD GH Actions I am having a really hard time justifying not just using a PAT (on org or generic user with access to all the private/innersource repos) or even SSH (generic user within org with access to all private/innersource repos).

The biggest reason is because you have to have an org or user who "owns" the GH App anyway. So the GH App doesn't get you anything. It's just more hassle to maintain. The "additional rate limits" provided to GH Apps are for stuff that is going to hit the GH API all the time, but the occasional CI/CD build and release actions that hit the API extremely infrequently are definitely never going to come anywhere near those rate limits.

* https://docs.github.com/en/apps/using-github-apps/installing-your-own-github-app#installing-your-private-github-app-on-your-repository
