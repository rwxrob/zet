# ProtonMail is Still Better Than Gmail

I read this tweet from ElleArmageddon, the "Directory of Security
Engineering" (living in SV, California) and I was blown away:

> In light of the protonmail kerfuffle, I feel compelled to remind you:
>
> Just use gmail.
>
> If you do not want Google reading it, email is not the appropriate
> format for your communication.
>
> Please just trust me on this.

The Russians wouldn't block ProtonMail if it didn't work.

Everyone knows email has had a problem since it was invented, but so did
FTP, telnet, gopher, finger, print services, and HTTP. No one wanted to
listen to the cypherpunk elites who turned out to be prophets predicting
the failures of today's routed information systems that do not focus on
content encryption "at rest" instead of trying to secure each of the
"pipes" along the way.

I could not reply to Emily's tweet because they (their preferred
pronoun) have replies off, for obvious reasons. Anyone who claims that
you should just be okay with sending Gmail and that there is no
difference if you don't want Google to read it doesn't understand basic
cryptography or how it is implemented at ProtonMail. Perhaps she does
and just prefers a click-bait tweet over an actual explanation. 

What I think Emily means is that you should never do anything online
that you don't want public in *any* system (email included) unless you
encrypt that content yourself using GPG or some other means, and at that
point you might as well use another method of transporting your content
because the route of your email *can* be tracked.

> GPG/PGP encryption is a part of the *standard* library in Go, another
> reason hackers love Go.

Content encryption is always stronger than tunnel encryption. If that is
what Emily is saying, then I agree with that statement completely. But I
won't know because she tends to prefer Twitter to actual writing. 

As angry as I am about the ProtonMail violation of good-faith as
promised in Andy's TED talk about privacy, I must point out that even
though ProtonMail uses tunnel encryption, its email system is 100%
unreadable by *anyone* unless they hack your personal computer on which
you are viewing the email *through the web interface*. This has been
overwhelmingly confirmed by independent security people outside of
Proton.

ProtonMail *is* secure when done properly because two different key
pairs are used, and the encryption is done and maintained *on your
computer*. You can even provide your own keys. Therefore, if you use
ProtonMail's mobile app or the bridge (which is nice if you like things
like `mutt` and `procmail`) then nothing ever leaves your computer
without being encrypted with the keys only on that computer and there is
no way to compromise your security through the app even if ProtonMail
itself wanted to. Obviously, it's more complicated than that, but you
get the idea.

> 💬
> Probably a good time to mention that the ProtonMail web site interface
> has never (and will never) be free from the possibility that
> ProtonMail has a gun pointed to their head and writes an exploit just
> for a specific person. Because the app is loaded every time you go to
> the site, it is open to such vulns. But the bridge and the mobile apps
> are open sourced and only updated when you force them to be.

Emily seems to suggest we should all just throw email out completely,
that we should just kill the expectation that *any* email can ever be
secure and therefore email should just fucking die. As much as I
sometimes want to agree with this -- especially after all the phishing
happening through email -- it's just not appropriate. There are plenty
of reasons not to want anyone to read your email. After all, 2-factor
authentication uses it, your bank sends you stuff, your doctor sends
records.

Emily quickly walked back her unintentional endorsement of Google, but I
still feel it worth mentioning that there are many things that I never
want Google to know. "Gmail is essentially public" is something I tell
people, which agrees with Emily. But there are still very many things
that go through unencrypted email that I *never* want Google, or those
who pay Google or hack Google, to know that easily.

The only way any email on ProtonMail is truly protected is if the sender
and receiver *both* have ProtonMail accounts *or* you turn on the
encryption option for a specific email and force the person receiving it
to login and use their web browser to read it, a web browser, that if
forced by a government, could be hacked specifically to get your keys
from you. And it's very unlikely your non-technical friends and family
would bother with that sort of thing.

Emily's choice of Twitter causes the perception that she is saying,
"You should just use Gmail." She's not saying that at all. (Even though
she used those words.) 

Emily indirectly implies that ProtonMail provides no additional
protections, painting the safety that ProtonMail *does* provide as
inferior to other things without saying what those things are. Emily's
inferred response is, "Well you should never do anything you want
private on ProtonMail anyway, which is why Gmail is just fine." 

Let's guess that Emily meant stuff like Signal (again we have to guess
because she prefers confusing tweets over actual writing). While it is
true that Signal is a much faster form of communication, it's an
entirely *different* form of communication. You simply cannot send large
amounts of data over Signal or Slack and still have a 'man in the
middle' that you can track destinations even if they cannot see content.
Messaging has revolutionized how we do work and communicate, but we
still need *something like* email for larger documents. (Disclosure:
I've worked on FOSS KEG ideas related to this question.)

Suggesting that 'Gmail is just fine' (essentially) is irresponsible from
someone claiming to understand security and privacy issues. I suppose I
should have expected this level of completely obfuscated arrogance from
an American security person leading the charge for a company in Silicon
Valley. But it is dangerous because people heeding her tweet will
continue to do insecure things and be okay with it whether or not they
misunderstood what she was saying, again because she preferred a
click-bait tweet over actual writing, something very common from the SV
set.

And by the way, saying the words, "Just trust me on this" -- especially
if you claim to be a researcher -- is absolute objective proof you *do
not have my best interests at heart* because you are asking me to
dismiss my own critical thinking and analysis. Nothing -- I mean
*nothing* -- screams "YOU SHOULD NEVER LISTEN TO ANYTHING I SAY" more
than saying "just trust me, bro." I'm blown away by that attitude.

The appropriate alternative way to express that tweeted sentiment would
be, "This is my conclusion based on what I've outlined in this piece of
writing that you can validate on your own." This encourages people to do
their own research and critical thinking while providing the convenience
of your conclusion up front. Instead, she exposes her heart-felt belief
that you are too stupid, uninformed, or lazy to draw your own
conclusions based on her undocumented logic.

    #protonmail #gmail #google #infosec #fails @ElleArmageddon
