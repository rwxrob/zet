# SKILSTAK on YouTube shorts/TikTok?

The breakdown of SKILSTAK content organization is still very relevant, but I wonder if all of the content could be broken down into one minute video shorts combined with written material that has more of the searchable details.

Section | Size | Title
-|-|-
START    |  3  | Start your tech career
BASIC    |  2  | Master basic computer skills
WEB      |  3  | Create a basic web site
LINUX    |  4  | Get a Linux machine
TERMINAL |  8  | Learn the terminal
CODE     |  12 | Learn to code
C        |  8  | Learn C for understanding
GO       |  12 | Develop enterprise software in Go
LXC      |  3  | Leverage Linux containers

## Still very needed

Today I spent most of it going through some of the worst shell code I have ever seen and this stuff is in production. It violates so many of the basics of shell scripting, doesn't even pass `shellcheck` or `shfmt` and has absolutely no sense of minimal sub-shells usage and variable scope. This is why there are so many bugs and massive security flaws in the world. Know one seems to know this stuff, not even the very highly paid professionals out there. They are great people, but just so freaking clueless about Linux terminal usage and shell scripting in general. Why? Because *no one* is teaching this stuff correctly.

For example, next time you run into someone who claims to know how to script in shell ask them *specifically* what the following code does?

```sh
: "${K8SAPP_NAMESPACE:=harbor}"
```

99% of professionals who have written code on Fortune 500 companies have no fucking clue what that code does or why it is so valuable. That's just one tiny example. Almost none of these "professionals" can even explain what a UNIX filter even is and how to invoke one from the command line while still in Vim.

In short, it took seeing this shit to want to do something about it. Someone has to. I can't just sit back and relax and watch the UNIX/Linux world crumble into idiocracy. It is actually something I can do something about. It lit a fire under me again to someone organize this stuff in a TikTok world where people might actually learn something along with their cat videos.

## Will they read anything?

People don't read these days. This makes the people who *do* read seem like super heroes in comparison. Still, when presenting the traditional SKILSTAK content it needs to be digestible enough to keep people engaged and interested. This is the reason so many others have failed. The stuff is just too boring and dense or just to wrong and inexperienced. YouTube is filled with absolutely horribly bad tech content that could actually seriously damage a beginners trajectory and, at a minimum, waste their time.


