# Lost Art of Rapid Prototyping

Once upon a time, RAD (rapid-applications-development) was all the rage
and you could argue that this led to the dark times of interpreted
languages in production systems. The world seems to have woken up from
that and now trust strictly languages of significant size.

However, the skills and approach of rapid prototyping still holds value.
After all, software development is critically dependent on machine the
interface and functionality with the users. Creating a user story by
outlining how it is used is still a very solid practice. And when that
tool involves something running from the terminal or command line
writing in a language that is indistinguishable from a compiled binary
is the still the fastest way to do that. There are are only a handful of
practical options in that arena: Bash, Perl, Python, and Node. It really
depends on what is being integrated into the prototype. Does it have a
hefty web element? Maybe Node, maybe not. Curl does pretty much
everything these days. My pick remains Perl because so much of the
prototyping involves dealing with text and taping together other
best-of-breed tools to create something that just works to demonstrate
how a thing *will* work form. The existence of `jq`, `yq`, `curl`,
`auth`, and many more tools have made this even easier.
