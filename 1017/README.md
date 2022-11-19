# First Go Bonzai Project Actually Paid to Do

Technically, I was paying myself to do all the Go coding I did in 2014
for `skilbot` and the student password management utility and my
Minecraft Server deployment automation. It was all well and good and got
me to where I am today. 

Well today, I just released v1.0.1 of the `kubectl-login`/`klogin` for a
huge multi-national and it feels pretty good. I cannot share the exact
code, but it used Bonzai to great effect making it very easy to read and
understand.

I don't think I can overstate how amazing just dynamic help
documentation is. Instead of describing where the file is that it
updates after getting the tokens from OIDC is actually shows the path to
the file in the man-page-like help information that is embedded in the
command itself.

Using `z go dist build` and the `gh release` command I didn't need any
complicated Docker build environment at all. It all just works, 'cuz Go.

Why people develop in any language other than Go for this sort of stuff
completely blows my mind. It's so fucking easy to develop, deploy,
release, and maintain. No wonder Go is the industry standard for this
type of thing. Other languages can't even come close. And because my
project is a Bonzai command branch as well, any other teams at our
company who want to add out cluster `klogin` can add it to their own Go
monoliths *with a single fucking `import` statement.* No other language
on planet Earth allows that at the moment.

I'm just gonna say it: I'm turning writing operations and hacker Go
Bonzai tooling into a full-time job somehow. I just have to. It's time
the world saw how easy command line composite apps can be.

    #golang #bonzai #coding
