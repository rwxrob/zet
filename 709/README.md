# Yet Another Dumb-Ass Compares Zsh to Bash

The shit on the Internet written by zsh script-kiddies is so fucking
wrong these people should be embarrassed. They are creating a dangerous
environment for learning *good* shell development practices. Eventually,
I'll address every single one here, but let's start with the easy ones:

* *"Hash data structures are supported in Zsh that are not present in
  Bash"* Yes they are. I use them every fucking week.

* *"Zsh is more interactive and customizable than Bash."* No it's
  absolutely not. In fact, Zsh's "customizable" nature makes it
  completely impossible to transport all your configurations (such as
  functions) in a single file between systems. I think this idiot really
  means that you can use oh-my-zsh with zsh. But, the same exists for
  bash (if you are into that sort of thing).

* *"Zsh has floating-point support that bash does not possess."* You are
  right, because it is dangerous to include it and build a false
  expectation --- especially in a language that claims to be 100% POSIX
  compatible. It absolutely is not. It's just fucking not. If you happen
  use any form of zsh for scripting (which is just so fucking stupid I
  don't have words) and then need to port it to a *true* POSIX shell
  like `ash` (as close as you can get anyway) then all those uses of
  floating point math will cause subtle and devastatingly undetectable
  floor division errors, you fucking moron. Don't believe me? Try it
  yourself with `shellcheck` and see what happens.

* *"The prompt look can be controlled in Bash, whereas Zsh is
  customizable."* How fucking stupid is this idiot?! You can control the
  entire fucking prompt and customize it to do whatever the fuck you
  want. Did this dick even read the bash man page, like, at all!?

I've had enough. I can't read any more. Maybe later. It makes me too
mad. Time to bet busy countering this moron with actually accurate,
verifiable, tested information.

Related:

* Zsh vs Bash \| Top 36 Differences You Should Know  
  <https://www.educba.com/zsh-vs-bash/>

    #rants #bash #zsh #linux
