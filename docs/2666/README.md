# SKILSTAK book + YouTube shorts/TikTok?

The breakdown of SKILSTAK content organization is still very relevant, but I wonder if all of the content could be broken down into one minute video shorts combined with written material that has more searchable details.

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

99% of professionals who have written code on Fortune 500 companies have no clue what that code does or why it is so valuable. That's just one tiny example. Almost none of these "professionals" can even explain what a UNIX filter even is and how to invoke one from the command line while still in Vim.

In short, it took seeing this shit to want to do something about it. Someone has to. I can't just sit back and relax and watch the UNIX/Linux world crumble into idiocracy. It is actually something I can do something about. It lit a fire under me again to someone organize this stuff in a TikTok world where people might actually learn something along with their cat videos.

## Will they read anything?

People don't read these days. This makes the people who *do* read seem like super heroes in comparison. Still, when presenting the traditional SKILSTAK content it needs to be digestible enough to keep people engaged and interested. This is the reason so many others have failed. The stuff is just too boring and dense or just to wrong and inexperienced. YouTube is filled with absolutely horribly bad tech content that could actually seriously damage a beginners trajectory and, at a minimum, waste their time.

## Book is best

I go back and forth on this all the time. Writing a tech book is a monumental undertaking and usually spans several years to get right. However, once a book is available it opens up doors to the largest number of organizations that want to use that content.

## Supplement book with video shorts

Something that I haven't encountered yet is a book author who has combined YouTube video shorts to cover the main issues from a given chapter or section of a book. That could provide the marketing and hook to get people to link to the online content of the book that is there.

## Searchable

No book is worth anything if it cannot be quickly searched from the web. Everything requires some sort of search interface today. But there are several approaches to searchability:

* Keywords
* GitHub
* AI
* Let Google (or whatever) index it

Making content searchable also usually means that all of it can be copied without your permission.

## Creative Commons?


## Income and support

The question comes down to trust. Can an author trust the people directly benefiting from content that takes seriously several thousands of hours to produce, edit, and maintain to pay them honestly for that effort? The answer, sadly, is no fucking way. People are shits and even the good ones always feel entitled to more than they deserve (including me). None of them can truly understand the level of work required to make this content available in its most digestible form.

One model for making money to support creating and maintaining a book has always been to make the source of the book entirely open and force people to pay for the printed copy if they want one. This is how "Learning the Linux Command Line" was published, even though no one should rely on it in 2024 given that it is well over 10 years out of date now. I purchased two copies of the printed book before I even realized it was available for free as well (mostly because the author never mentions that in the book itself).

The reality is that no one really wants a printed book in 2024, not even the slow-moving universities. So depending on this model for financial support of the project this is just not a possibility.

Unfortunately, this leaves self-publishing to a format that cannot be pirated easily and really the only way to do that is through Amazon.

### What about people who cannot pay?

This is always the question. People from other countries and economies unlike that of the author simply cannot pay even the most reduced rate for a book. This is a problem of work economics, not the author or publisher. It's not my fault that people in China can cheat and copy anything from any market at all and never pay a fucking dime for it even reselling it to others cheaper. Should they do that? Fuck no. Do they? All the time. In fact, they actually know that it undermines other markets and economies and they just don't care to ever play by any fair rules at all. But none of that is my fault, so why am I the one punished for it? Why am I the shit-head who won't release his hard work for free? Why am I the bad guy for putting a price on something I have created that another country cannot afford? I'm not the one who made those rules. Why should I be the one punished for it? This is why the very concept of open source is fundamentally broken at its core. Stallman's example of cookies doesn't hold up. "If you bring code to your school class you are obligated to bring a copy for everyone?" This is absolute bullshit. Implying I have a social contract to give everyone around me the product of my hard work for free just because it is "the right thing" is absolutely the worst of Leninism. Fuck no.

So what about the people who cannot pay? Honestly, fuck 'em. If they have an extenuating circumstance then they can ask. But even then, it isn't up to *me* to fund their charitable access to my hard work, that's up to some other charitable organization to fix and have *that* organization *purchase* copies for the poor souls who didn't happen to be born into the right circumstances. The assumption that content creators are personally responsible to sacrifice their own personal financial benefit for the good of the whole when they aren't the ones who fucking broke the system is fucking idiotic.

Unfortunately, this is why "advertising free" services are even adding advertising now. Advertising is the only way to fund "free" content for everyone. But advertising is not a model for making money from a book, a web site perhaps, but not a book.

## What about Udemy?

Udemy is shit. It is the Spotify of educational content. It gets wildly rich off the content creators and gives them practically nothing. It controls the prices and holds content creators hostage.

## What about just a paid web site?

Even though people will attack you as being the biggest asshole in the world for putting up a paid gateway to your content, this is the only *true* way to earn what you deserve. You control the access and exceptions and price as well as making sure the content is up to date.

## Conclusion

I've decided that the only thing that will be free are the YouTube promotional shorts that point to a paywalled web site that contains the full content for that topic. I'm gonna get fucking hate mail over this, but the people who have been "supporting" the effort financially are so fucking fickle I can never create a maintainable income based on their whims. So fuck 'em. Even the extremely wealthy, single, silicon valley types don't have the money to fund an effort like mine even though they talk a big fucking game and say how much they want to support me. All words, no action. No more.
