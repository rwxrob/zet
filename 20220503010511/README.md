# Kubernetes Apps Require Changelog

I get pretty pissed off when I have to go through all the changes from
an approved Kubernetes project that doesn't even have a fucking
CHANGELOG.md file. I think the developers sometimes forget that this
shit is being deployed in enterprise production servers all over the
fucking globe. People aren't just going to take your word for it or read
the commit history to know what you changed --- and how you put their
enterprise at risk. No, and even *with* a good CHANGELOG.md there's a
good chance most operations teams are going to vet and comb though your
shitty Helm chart and everything else you feel is okay to put on any
system on the planet, because history has repeatedly taught me (and most
veterans) that no matter how good you think your software is, it's
probably still shit. "Beware the .0!" as they say.

The projects that really have my respect immediately are those who
actually have a release management team who take the time to create that
list of changes. And, by the way, I don't do that for any of my
libraries because I don't feel obligated to until they are at v1.0. But,
let's be honest, people are going to use it long before that. I need to
start myself by forcing every fucking change I make to be captured in
human readable form in the CHANGELOG.md. I vow, today, that will never
push a commit without having some mention of it in just such a file.

This also turns out to be a mandatory file addition to the standard
`k8sapp-` template. In my case, I can keep it up to date and in sync
with all the changes that I feel are significant enough to bring up in
an enterprise change ticket. I know with all the CI/CD shit floating
around polluting the IT waters today that suggesting someone use a
change management system seems old fashioned. It's not. It's fucking
not. It forces a person with a brain to consider the implications and
delineate them for others rather than trusting the developers with that
shit. Who the fuck *ever* trusts a developer? I certainly don't, and I
*am* one. Maybe that is why I don't trust them.

    #rant #changelog #coding
