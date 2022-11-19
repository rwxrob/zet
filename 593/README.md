# Use Git HTTPS URLs for Repos You Use Also at Work

Workplaces, schools, and other such organzations usually use some sort
of web proxy that allows requests out through the firewall to be
redirected properly. What these proxies normally don't allow is any
outbound git or ssh traffic. So it makes sense to use the web (https)
form of URLs where normally you would use git@github.com. We'll see how
this holds up over time since GitHub has said it is moving away from
HTTPs, but mine worked without any password prompting at all making me
thing that somehow my keys are still being used.
