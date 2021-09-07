# Don't Use Gmail, ProtonMail Still Better

I read this tweet from ElleArmageddon, the "Directory of Security
Engineering" (living in California) and I was fucking blown away by their
lack of clue:

> In light of the protonmail kerfuffle, I feel compelled to remind you:
>
> Just use gmail.
>
> If you do not want Google reading it, email is not the appropriate
> format for your communication.
>
> Please just trust me on this.

The Russians wouldn't block ProtonMail if it didn't work.

Apparently you should *never* trust Emily on anything, and definitely
not *pay them* for security direction.

I could not reply to their tweet because they have replies off, for
obvious reasons. Anyone who claims that you should just be okay with
sending Gmail and that there is no difference if you don't want Google
to read it doesn't understand basic cryptography or how it is
implemented at ProtonMail. 

What I think they means (but don't know because apparently writing out
her full position in something other than a fucking tweet was to much of
an infringement on her their schedule), is that you should never do
anything online that you don't want public unless you encrypt that
content yourself using GPG or some other means. I agree with that
statement completely. Content encryption is always stronger than tunnel
encryption.

But what they fails to point out is that ProtonMail email is 100%
unreadable by *anyone* unless they hack your personal computer on which
you are viewing the email *through the web interface*. This is because
two different key pairs are used, and the encryption is done and
maintained *on your computer*. If you use ProtonMail's mobile app or the
bridge, which is nice if you like things like `mutt` and `procmail`,
then nothing ever leaves your computer without being encrypted there and
there is no way to compromise your security through the app even if
ProtonMail itself wanted to.

> 💬
> Probably a good time to mention that the ProtonMail web site interface
> has never (and will never) be free from the possibility that
> ProtonMail has a gun pointed to their head and writes an exploit just
> for a specific person. Because the app is loaded every time you go to
> the site, it is open to such vulns. But the bridge and the mobile apps
> are open sourced and only updated when you force them to be.

There are plenty of reasons not to want anyone to read your email. After
all, 2-factor authentication uses it, your bank sends you stuff, your
doctor sends records. There are still very many things that go through
email that you don't want Google (or anyone) to read. On this point
I will agree with Emily, just because you use ProtonMail doesn't mean
those things are protected. The only way any email on ProtonMail is
truly protected is if the sender and receiver *both* have ProtonMail
accounts *or* you turn on the encryption option for a specific email and
force the person receiving it to login and use their web browser to read
it, a web browser, that if forced by a government, could be hacked
specifically to get your keys from you.

Emily misses the boat by suggesting that you "should just use Gmail" and
suggesting that you should just not do stuff using it you don't want
Google to read. Emily continues to suggest that ProtonMail provides no
additional protections, painting the safety that ProtonMail does provide
to those who use it as inferior to other things. While it is true that
Signal is a much faster form of communication, Emily does not say so
explicitly (because it wouldn't fit in her tweet). 

Emily's response is, "Well you should never do anything you want private
on ProtonMail anyway, which is why Gmail is just fine." 

This is irresponsible from someone claiming to understand security, but
it is not unexpected from an American security person leading the charge
for a company in California. People heeding her tweet will continue to
do stupid, dangerous things and be okay with it.

And by the way, saying the words, "Just trust me on this" -- especially
if you claim to be a researcher -- is absolute objective proof you *do
not have my best interests at heart* because you are asking me to
dismiss my own critical thinking and analysis. Nothing, I mean *nothing*,
screams "YOU SHOULD NEVER LISTEN TO ANYTHING I SAY" more than saying
"just trust me, bro." I'm blown away by that attitude.

The appropriate way alternative way to express that tweeted sentiment
would be, "This is my conclusion based on what I've outlined in this
piece of writing that you can validate on your own." This encourages
people to do their own research and critical thinking while providing
the convenience of your conclusion up front. 

    #protonmail #infosec #fails
