# NeoVim is Shit and Ruining New Developers

NeoVim, which uses the `nvim` command, is unfortunately a popular
replacement to Vim. This is bad. It is ruining beginning developers
while providing no additional value for most users because they jump in
and learn everything the NeoVim way rather than progressively adding to
their `vi` and `vim` learning. In other words, `vi` -> `vim` -> `neovim`
would be a reasonable learning path, but beginners don't do that and the
NeoVim team actively recruits people to their cause without any
consideration for the important of a progressive learning approach.

> My disappointment about NeoVim is not personal. Good people (some very
> close to me) use and advocate for NeoVim, and I actively campaign
> against it. I fucking hate it. (But hey, it's the same for
> crypto-currency as well.)

NeoVim's most significant failure is not technical at all. The NeoVim
design team has demonstrated a complete lack of understanding of Vi's
core value proposition as well as a total disregard for the fundamental
Unix philosophy. The bloated, buggy result is `nvim`. 

Here are the advantages people usually present when asked why anyone
should consider using NeoVim and include an explanation about why they
are actually *dis*-advantages. They include reasons [documented by the
NeoVim project itself.](https://neovim.io/doc/user/vim_diff.html)

## "Better Configuration"

NeoVim looks in `$XDG_CONFIG_HOME` for its configuration files which
means that it follows the `~/.config/...` location convention that is
now the Linux standard. I love this! I love their concern for this
standard.

Unfortunately, after more than two decades, no one cares because you
*already* are maintaining your Vim configuration in a dotfiles repo and
providing symbolic links.

Besides, moving the configuration file is downright stupid given the
decades of precedent with `~/.vimrc`. The main reason you picked Vim in
the first place was because Vim is on just about everything and copying
over your configuration is a simple matter of `scp ~/.vimrc you@remote:`
and your done. Boom. No other configuration needed. Somehow the NeoVim
team didn't figure that out, probably because they are used to
essentially turning their NeoVim editor into a watered down version of
Emacs that can only run on the single system on which it is configured.

## "Better Defaults"

The second thing listed on [NeoVim's comparison
page](https://neovim.io/doc/user/vim_diff.html) is the 42 different
defaults from Vim. These are completely and totally irrelevant because
*anyone* using Vim should *always* disable all the defaults and begin
with a clean slate in their `vimrc` file. The very fact that the NeoVim
team thought that having different defaults actually matters at all
shows how disconnected that design team is from how Vim is actually used
professionally. Again, a symptom of Emacs-envy.

## "Multiple API and Plugin Support"

Vim has this as well but you should almost never use it, that is, unless
you want to make Vim into VSCode or Emacs or Sublime. Seriously folks,
the entire emphasis of the NeoVim project and priorities demonstrates an
utter cluelessness about the actual value proposition of picking Vim in
the first place --- the biggest being *full shell integration for
extensibility*, not supporting Lua and NodeJS plugins. NeoVim has made
itself into a serious joke among those who know and use Vi/m as has been
down for decades for all the right reasons.

Having a clearer internal API is a compelling reason to consider *any*
project, but it doesn't hold any weight with the end user. Think about
[Wayland vs X](https://duck.com/lite?kae=t&q=Wayland%20vs%20X), for example.

## "Changed Features"

Every single feature that has changed is ridiculously irrelevant to
anyone who actually knows how to use Vi. Things like `json_decode` are
just silly when commands like [`jq`](/tools/jq/) exist. They even
renamed `viminfo` to `shada` for nothing but vain not-invented-here
reasons. And Lua and Python support? Pffff. Please. You can be glad you
learned to use Vi/m correctly and without a bunch of unnecessary bloat
that would directly affect your performance on *every* other system with
Vi while *diminishing* your ability to actually use your most powerful
tool, the shell in which Vi/m is running.

What is even worse is that NeoVim has actually corrupted the *expected*
behavior of current Vi and Vim options and Ex commands. This is simply
dangerous and stupid. It creates an unnecessary rift in muscle-memory
that you *never* want to burn into your brain.

## "Missing Legacy Features"

The `if_perl` has been dropped. Nothing screams "we are all morons" more
than dropping Perl support from something that has had it for 2 decades
just because you buy into the trendy Perl-hate. Perl has the world's
most powerful regular expression engine as has been proven over and
again by its integration *into every other language* with regular
expressions including Python, NodeJS, even Bash. To blindly remove
support for syntax used by Vim users that integrate Perl (albeit
foolishly when they should have just integrated shell command filters
instead) is just plain clueless and downright stupid.

## "Removed Features"

NeoVim *removed* several core tools used regular by Vim users for
seriously important use cases:

* `ex` - binary not installed (vim does)
* `:ex` - not accessible from vim command line
* `view` - cannot run `vi` in read-only mode
* `vimdiff` - cannot compare files (big secops thing)
* `:shell` - no subshell from vim command line
* `:smile` - that's just low (soooo much bloat there)

Again, incredibly inexperienced decisions from people who *never
actually learned to use Vim* for anything significant in the first
place. The fact that they removed `:shell` completely confirms they
don't value shell integration which is the basis of all of Vim's
[magical power](/tools/editors/vi/how/magic/). The fact that they
removed `vimdiff` shows none of them have ever worked on any
cybersecurity project of any significance.

Come on, they didn't need to remove `:smile`?! That's just low.

## "More Accessible Team"

Yeah, just no. No one should believe that for a second. If anything, the
Vim team is simply more capable and discerning than the NeoVim team and
by the looks of the NeoVim project priorities this seems to be
objectively true. Brahm's only good thing to say about NeoVim is that
"they have a nice web site".

## "External Plugins in Separate Process"

This might be true, but again it is irrelevant because no one should be
that dependent on plugins in the first place. In fact, making plugins
running in a separate process and thread is a symptom that they are
doing the internals completely wrong by allowing plugins to take a far
greater position in the overall runtime. This is not Microsoft Visual
Studio we are using here.

## "Better Support for Alacritty"

While Alacritty is an amazing project this claim makes absolutely no
sense whatsoever. It's an editor running in a terminal. Making a
decision to use a ubiquitous terminal editor based on which terminal
application you use it hilariously stupid and irrelevant. That's like
arguing back with "Well I use Vim because it works better with Xterm2."
Who cares?!

## "Gives Vim Healthy Competition"

Giving Vim competition certainly cannot hurt. But anyone who actually
knows how to use Vi/m and gives NeoVim's list of differences a solid
review will realize NeoVim is absolutely no competition at all. Vim is
installed on literally millions of Linux systems dating back more than
three decades. NeoVim *might* be installed on maybe 10,000 systems tops.
There is *zero* competition. NeoVim does not even have a 1.0 release
yet.

## "It Has Panes"

So does Vim, but you should never use them unless you are forced. They
are an unnecessary and useless Vimisms that are better replaced with
learning to use TMUX panes or even `screen` windows instead since they
work for *any* application not just Vim.

## Bugs? Stability?

It has been reported that NeoVim contains a lot of bugs and stability
issues. That is no surprise at all given the massive, unnecessary
scope-creep the NeoVim project team has *deliberately* chosen to
maintain. 

Any serious professional understands the importance of the Unix
philosophy of doing one thing well and making sure it integrates with
everything else. NeoVim --- with all its unnecessary bloat --- is a
serious departure from that philosophy and will continue to remain
unstable and buggy because of it. It really is a shame that the NeoVim
development team simply cannot see that.

## NeoVim Has to Prove It is Needed

I'm tired of being immediately attacked for not using the editor that
comes by default on millions (if not billions) of UNIX and Linux
systems. People who don't know better (who are usually avid oh-my-zsh
fans, despite the zsh team's active campaign against it) seem to think I
have to justify *to them* why I am *not* using it. 

Here's the thing, the burden of proof is on them. *They* have to justify
to *me* why I should use their immature crap that hasn't even got a 1.0
release out yet nor an official package for Ubuntu or Debian (still at
0.4.4 as of this writing).

Seriously, how the fuck do you have the gall to try and tell me that I'm
wrong because I'm not using and advocating your shitty alpha software
for my daily professional work instead of the production `vi` and `vim`
that comes with not just my system, but millions of others.

That level of clueless arrogance is only possible from a group of people
that thought rewriting `vi` in Lua was actually a good idea worth
pursuing. They are certainly entitled to it. That's the beauty of open
source. But I'm also free to think that is the dumbest shit to come out
of open source in a decade.

## Dude, why so harsh on NeoVim?

In short, NeoVim is creating a bunch of very dangerous --- and in some
cases --- unemployable beginners who have burned NeoVim practices into
their brains and muscle memory. That's irresponsible and it pisses me
off. 

The first thing any responsible NeoVim user or advocate should say
to any beginner is, "Do NOT learn NeoVim until you have mastered `vi`
and then `vim` first" but obviously they never do that. Instead, they
blindly seek to corrupt an entire generation of new terminal users
causing them to mistake this horrible alpha software --- that's
internally closer to Roblox than Linux --- as a thing they call Vim.
It's just not.

This review started out much more objectively. But as each point of
difference stated by the team itself was examined, the level of
hilarious collective cluelessness exceeded my ability not to completely
roast it. There is simply nothing good to say about NeoVim at all. It
really is just that bad. The world is worse off for it existing. All it
does is confuse beginners who later regret it. The world does not now,
nor ever has needed, yet another dozen ways to write NeoVim plugins. It
is the *wrong* direction.

Perhaps if they had made another editor and gave it another name that
would have been better. Rumor has it they might actually be doing that.

Put comically, the NeoVim projects seems like a bunch of people got
their feelings hurt trying to get their stupid, bloated ideas accepted
into the Vim project so they started their own while waving their pretty
logo and chanting "We're more open. We're more open." 

Fact is. The clueless cult of over-engineering bloat makers never knew
how to use Vi in the first place. Just ask them what `:!!` does and how
many times they use it throughout the day. Most can't even tell you.
Their too busy dreaming up more ways to overcome their Emacs-envy and
making a terminal version of VSCode with a bad name. They don't know
`vi` and frankly don't understand Unix philosophy and never did.

## See Also

* <https://neovim.io/doc/user/vim_diff.html>
