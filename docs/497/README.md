# Noob Gets Reamed for Oh-My-Zsh and NeoVim in Prod

TL;DR; You can't take your Neo-fucking-Vim plugins and your pretty
little Oh-My-Shitty-Zsh colors into a production container. Sometimes
you'll be lucky to have `vi` (not `vim`) and an *actual* shell (that
isn't BusyBox, which is a multicall app, not a shell).

*The following is based on actual events. Names have been changed to
protect the guilty.*

Below is a chat that happened today in my live stream. While I hold
nothing personal against anyone who participated, I'm not fucking
sugar-coating this. It has to be called out. This will save people the
hassle of either getting fired or reamed a new asshole by their senior
team members. This noob is seriously lucky to still have his job.

This is why I go to such great lengths to help people understand that
all the shit other streamers and YouTubers do is *not* professional,
it's just not. There's no fucking Arch Linux in production. There's no
Oh-My-Zsh. There's not even Zsh. Often there's no Vim (let alone that
shitty monstrosity that doesn't deserve the Vim name).

These other technology YouTubers and streamers (who love to been seen
and have cutesy icons and cut-scenes and keyboard cameras and bounce
around on bouncy balls and play with all the memes and talk like they
are perpetually hype-casting a shitty League of Legends game) never say,
"Only do this on your own systems, never production" and so all the
noobs stuck to their sticky fly-strip stream end up coming away with
seriously bad ideas about how enterprise technology works. These people
have never even heard the term "change management" in their fucking
lives. They don't know or care about "4-9s uptime" and they are the
reason the BOFH became a thing.

So these noobs think that adding pretty things to prod will be their
pro-active contribution. Then you get this.

(By the way, it has nothing to do with "being a boomer", says this
ageist noob piece of shit.)

```
Noob: hello all
Noob: busy day, sr. devops guy got really mad with me lol
Chat: ^ hello
Noob: made me uninstall oh-my-zsh off the prod instances.
Noob: ya'll use that?
Chat: I just use vanilla terminals
Chat: with shopt autocd
Noob: he said we didn't need that in prod but i think it improves the experience
Chat: "My Machine ,My rules"
Noob: won't let me do nvim plugins either so i emailed his boss. we'll see what he says
Chat: did he say why ? XD
Noob: said that he didn't want all that bloat on the prod systems
Chat: but it's better
Noob: he's just a boomer
Chat: who did not want what?
Noob: my sr. devops manager
Noob: threatened to take away my prod access
Chat: did he seems afraid of ur wizardry skills
Noob: well not a wizard just trying to make things better
```

Think about it. Why do you think something as minimal as BusyBox or
Alpine is the *most popular image* for base containers? There's a
fucking reason. Now imagine throwing away all those optimizations
because you're a noob who doesn't know how to fucking bind mount volumes
and other shit to develop and work on them locally. Instead, you are
going to bloat the entire fucking base image in production.

Seriously, you pull that shit with me and it would be your first and
only warning. Most would fire you on the spot for the level of
absolutely unprofessional cluelessness. Hate me if you want, but you
might just keep that job a little longer.

