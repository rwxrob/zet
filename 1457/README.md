# Leave TMUX and Vim Buffers Separated

I thought using the Vim plugin that automatically combines Vim's
primary buffer with the TMUX buffer would be a good idea. It's just not.
The reason is because I've come to use both buffers simultaneously. For
example, let's say you grab some test output and went to dump it into
your unit test case but need to make some room first. You switch to your
test window and use the normal `Leader-[` to grab it. Then you switch
back to your unit test code and realize you need to make some room and
clean stuff up before the paste. So you start deleting and such. But
every time you do you fill the main Vim buffer, you know, the one that
would have contained your TMUX content if you were using the naive
plugin. So then when I go to `Leader-]` and paste there's nothing there
except for what I just deleted in Vim. So this looks like yet another
case where *not* adding extra shit is what you really want, surprise,
surprise.
