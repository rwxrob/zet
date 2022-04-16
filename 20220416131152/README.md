# GitHub Personal Access Tokens, Better Than Oauth

These things are great --- especially for command line applications that
don't have a web interface. I created `auth-go` once upon a time to
handle all of that by firing up a server temporarily on `localhost` so
that the "redirect URL" could set to it to get it to work. That's
because the "three-legged" Oauth flow is fucking brain dead (and always
has been). It's designed to "protect" applications from having to put
the credentials inside the app, to keep all that server side, but it
*completely* discounts the needs of command-line authentication flows. I
fucking hate when a command line app forces you to "open your web
browser" so it can do what it needs to. In that sense, OAuth is one of
the biggest architectural failures of our time. No wonder the original
creator abandoned the project in disgust.

But, there's hope in "personal" access tokens. These things use Basic
HTTP Authentication over TLS to serve as a plain-ol password. They
assume you are protecting them and can be set to expire and stuff like
anything else. They also have scopes, which is very critical for things
like GitHub Enterprise API public repo interactions that are not allowed
without a token (unlike the public github.com site). You can create a
non-expiring "personal" access token as a user with the permissions to
the repo that you need and just use that.

GitHub might not like that this is easier to use than "GitHub Apps" that
they try to push on you under the organization. Those "Apps" have all
the fucking brain-dead web-only shit built into them. Unfortunately,
there is not an equivalent of "personal" access tokens for an
organization. The great irony is that "personal" access tokens actually
work better for more enterprise command line tools than anything under
the "organization" scope.

All of this shit reminds me that I really do need to package and codify
my `auth-go` stuff better so that anything that is forced to do the
three-legged (brain-dead) web Oauth thing can cheat and set
https://localhost:23443 as the callback URL. It just feels so dirty to
do it knowing that personal access tokens exist. It isn't something I
can get behind for enterprise applications because you cannot be sure
that any given port on `localhost` will ever be free, or that the right
thing will be listening. In fact, setting `localhost` for any
Authorization Callback URL is a major security bug waiting to be
exploited. Anyone can put something on the system that
man-in-the-middles that flow and keeps it. But, it's no more risky than
having to store that "temporary" token with refresh token someplace on
in the clear on the local system, just like every web browser is
required to do for anything that has Oauth. Basically, if someone hacks
into a system with user-level permissions, they have access to *every*
web site that person has authenticated with using their local web
browser. It's a trivial matter to mine all those tokens out of their web
token and session cache and do all kinds of shit as them from their
machine using terminal-driven web clients that set themselves as the
User-Agent of the owned browser. In fact, sometime in the next year I
plan on exploiting the shit out of how broken all that is. Another
reason I need to finish my `web` Bonzai tree so that I can have a full
web client in any composite binary payload.

The bottom line: there is no *easy* way to give a command line
application access to scoped resources hosted on GitHub Enterprise (or
really any Oauth-centric thing). The `gh` GitHub command line tool does
a pretty damn good job of this without punting and using
`localhost:234`.
