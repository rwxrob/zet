# Replace `api.github.com` with `[host]/api/v3`

After a bit of localized testing (at work) I see that the secret to
getting your API that works against the public GitHub API to work on
Enterprise is to just replace `api.github.com` with `[host]/api/v3`
(assuming that is your version). Don't forget to create a developer
token with crazy-ass permissions in order to be able to do even the
simplest of queries allowed against the public one. I'm sure that is
because API quotes are totally different for Enterprise.

    #github #api #tips
