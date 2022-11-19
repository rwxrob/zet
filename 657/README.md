# Ephemeral (Cloud) Dev Environments are Shit

Got an email from GitPod today. I fucking hate GitPod. The entire
company is built on the moronic premise that developers *must* have
Internet access to do their work. I mean just listen to these morons:

> Ephemeral dev environments can improve this: no more local development
> environments mean that it will always work on your machine, no matter
> what machine you have. You can quickly access your whole environment
> in a browser that new engineers can easily jump right into.

I love "quickly access" in particular. Spoken like a true web dev with a
GUI binky in their mouth. By the way (*you fucking moron*) working in a
web browser is not "on your machine" and yes I get what you mean. What's
your next play? Trying to sell "network appliances" and "the
network is the computer" bullshit?

Yeah, no, you can't even remember how fast that shit died swallowed
whole eventually by the poster child of brain-dead tech companies: 
Oracle.

The industry has already tried this and decided that developers actually
need to be able to get shit done without an Internet connection. 

Oh my GOD! Can you believe it? Just imagine.

"I have some work to finish up on with the UX, I'll just work on that on
my flight. Oh wait, I won't have reliable Internet on the plane. Oh
well, looks like I'll just get drunk and play League, I mean Halo, I
mean Tetris."

In fact, that's the very premise of Git in the first place. The reason
we `git clone` things is to get an *actual local* copy and work on. Can
you even imagine suggesting to Linus Torvalds that he needs a shitty GUI
web browser to code on the kernel? We are talking about a guy who has
gone on record saying that "Web developers can't really call themselves
developers."

Then you have this one:

> The most important part of developing a feature is developing the
> feature, so why waste any more time on anything else?

Oh I don't know, because you are expected to actually know what the fuck
you are doing? Perhaps you should actually understand the system that is
going to host your shitty app. What's that? It is too big and bloated to
run in a container on your local system? Yeah, you have bigger problems.
Rather than propose ways to get around the biggest problem of all you
just address the problem of the absolute shit you have created and how
to break it up. Guess what, people are *doing it* successfully all over
the world, just not you, idiots. You are free to be morons, and I'm free
to call you morons. Maybe you should apply for a job at Netlix, I hear
they love hiring complete idiots.

Where do these moronic ideas come from?

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

    #rants #gitpod #monorepos #containers #devops
