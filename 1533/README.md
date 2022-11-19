# SSH and TMUX Into Live Streaming Rig

Say you don't want to be locked into your streaming rig all day while
streaming even though you wouldn't mind sharing your work (from the
terminal) with others during the day. For example, you have a laptop and
want to not necessarily stream from your laptop, but work from it,
mostly because it is more convenient and portable. (I love sitting in
different poses or even laying down while I code.) The solution is to
add `sshd` to your streaming system and `ssh` into it from your laptop.

Provided your terminals are roughly the same size and aspect ratio on
both your systems then you can start up a TMUX session (I do mine in
full screen) and just `tmux a` to connect to it. Then you can just
position that terminal however you want on the streaming system with OBS
(again, I just full screen mine) and everyone sees what you are typing.
Once you truly understand `ssh` and `tmux` this approach seems rather
intuitive.

Keep in mind that `screenkey` does not work with this approach since it
depends on the input through X (which is frankly quite stupid because it
could have just watched the `tty` device instead). [I wish it
did.][wish]

[wish]: <https://github.com/rwxrob/wish/search?q=screenkey>
