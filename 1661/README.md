# Avoid Twitch CLI (`twitch`) Configuration Gotchas

I stumbled on the following when trying to get the relatively new
`twitch` CLI command configured --- specifically to do anything with
`patch` HTTP calls:

**Don't forget to add `-u` and `-s` when creating the token.** Your
command should look something like `twitch token -u -s 'some:perm
another:perm'` with spaces between your permissions scopes. I ended up
having quite a few based on what I wanted to enable in my `iam`
application.

**Don't forget to set the redirect_url on the Twitch developers
dashboard to http://localhost:3000.** Anything else will fail because it
is setting up a local redirect (like I did in my `auth` tool).

**Be aware that the configuration file containing your secrets and token
is completely flat and open.** There is no way around this. Technically,
this is no worse than using Chrome or any web browser that stores your
cookies and sessions tokens on your local computer with your access
permissions. But still, be sure not to live stream opening that file. ;)

Related:

* Introducing the Twitch Command Line Interface Tool  
  <https://blog.twitch.tv/en/2020/12/17/introducing-the-twitch-command-line-interface-tool/>
* <https://dev.twitch.tv/docs/cli/token-command#app-access-token>

Tags:

    #twitch #dev #cli #tips
