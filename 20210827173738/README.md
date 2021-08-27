# Ephemeral (Cloud) Dev Environments are Shit

Got an email from GitPod today. I fucking hate GitPod. The entire
company is built on the moronic premise that developers *must* have
Internet access to do their work. The industry has already tried this
and decided that developers actually need to be able to get shit done
without an Internet connection. 

Oh my GOD! Can you believe it? Just imagine.

"I have some work to finish up on with the UX, I'll just work on that on
my flight. Oh wait, I won't have reliable Internet on the plane. Oh
well, looks like I'll just get drunk and play Halo."

In fact, that's the very premise of Git in the first place. The reason
we `git clone` things is to get a *local* copy and work on. Can you even
imagine suggesting to Linus Torvalds that he needs a shitty GUI web
browser to code on the kernel?

Where do these fucking moronic ideas come from?

My best guess is that script-kiddy web developers see the world through
their jaded, shitty perspective. Everything is a web app to them. And
their next million dollar idea will be related to putting something on
the Web. Doesn't matter though, because the even bigger morons with VC
capital to waste will throw it at these absolutely brain-dead business
plans. Oh well.

The sad part is that the problems they cite are real and need solutions,
just not web-based ones. Thankfully, containers *themselves* solve the
problem, that is, if you are using them and not following the completely
non-UNIX philosophy of creating "monorepos" that are 64 gigabytes big
(you fucking idiots). Hell, you can even do development on web projects
by putting it into a workspace container and then just sharing the
container. ***THAT'S WHAT CONTAINERS ARE FOR, DUMB ASS!***

I really need to calm down. But the level of base-line stupidity in the
tech software development world is just overwhelming. I blame all the
techs training in web development before ever learning Linux or the
UNIX philosophy.

Don't believe me? Imagine, for a moment, that you had 64GB Git repo you
wanted to tell Linus Torvalds about. What would Linus do? 🖕
