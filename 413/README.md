# Go Big Binaries Will Destroy Electron, Eventually

Electron is a bloated mess, but it remains popular because it creates
applications that appear to be independent. But what you end up with is
one version of Chromium running on your computer for every fucking
application. It's a ridiculous anti-pattern that any self-respecting
developer or architect would *never* authorize (yes, I know Discord,
Spotify, Slack, VSCode and tons of other significant "applications" use
it).

An alternative model is simply to use the web browser *already* running
on the system. That's where "big binaries" (a term I just invented) with
embedded static assets come in. You still get all the power of the
Electron back end, but you don't have to embed all of Chromium to get
it. Hell, you can throw out the web interface entirely and use Material
Design on Qt or GTK or any of the other graphics widget libs out there
now for Go. No one will know the difference and that app will be wicked
fast.

Speaking of apps, I wonder what the state of Go on mobile is. I really
wish Go wasn't pushing Flutter for that shit. Would have been good to
have them get behind Go on native mobile as well. Given the popularity
of Rust with front-end people I suppose that is another one to watch.
Even though it is a shitty choice for mobile app development, there's
enough popularity there to see people start trying it. But I digress.
