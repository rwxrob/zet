# Do Not Commit to `main`/`master` Without Telling

Just got burned seriously by someone trying to help me who blew out all
my development cluster changes with their own (which was bad enough
since I have to drop the entire namespace and start over) and then
committed their Helm chart "fix" to a Git repo on `master` for which
I was already working on a branch that now has serious merge conflicts.

"There was nothing on master and no branches."

Yeah, that's never a green-light to commit to master on a team monorepo.
Seriously, does this have to be explained to you? You never know who on
the team might be working on private, local branches (in this case on
stuff that had been specifically assigned to me) that will have
a serious merge conflict to that work even if you didn't "see" anything
in the posted, public repo.

Now I'm fucked.

I have to go through every single line of code and see what changed in
order to resolve the conflict --- and more importantly, what, if
anything, "fixed" the problem --- when all it would have taken to avoid
this would have been to say something like this:

"Hey, I'm going to commit to master, any conflicts I should know about?"

Now I'm the bad guy for complaining about the merge conflict.

By the way, if you want to turn a tense situation into an all out brawl
tell the person facing the merge conflict something like this:

"It all works now. Just `git diff` and `git stash` and you should be
fine."

That should be added to a top 10 list of shit you never tell your tech
peers. I went from annoyed to fucking pissed in five seconds. First,
because the asshole was explaining how to use `git` to me (still pissed
me off) and second, because he didn't have a fucking clue enough to know
how FUCKING STUPID that is to recommend. Then again, this is someone with
zero software development experience. And third, because he may have
been able to get it to work (which alone is awesome) but is now
a Simpson's character "henh-henh" all in the name of "helping" you.
There's no helping going on. Doing it and then not being able to explain
how you fixed it is bullshit --- especially when that is what you are
being paid to do.

Gotta love coding on an Ops team.

"PR what?"

    #rants #techlife #git #gitops #coding #100daysofcode
