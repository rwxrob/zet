# Why not CONTROL-C instead of ESC?

Using control-c instead of escape key (or equivalent, control-left-bracket) in Vi/Vim/NeoVim is a horrible idea.

* **Control-C sends an interrupt signal to the system**

You should come to expect control-c to stop and interrupt things, not switch editing modes. An interrupt means different things depending on the context and application being used.

* **Control-C also does not work in certain versions of vi**

If you are on AIX, Alpine, Solaris, BusyBox, BSD, and other UNIX variants you may not even have control-c support in your `vi` at all. Building it into your muscle memory makes you absolutely useless on these systems.

* **Use ESC, CONTROL-[, or CAPSLOCK instead**

The escape key is hard to get to, but there are other options. CONTROL-LEFT-BRACKET produces the exact same value as does ESC. But that requires a US keyboard (for which some internationals have actually purchased US keyboards). You can also remap CAPSLOCK (the original position of the ESC key) which uses the same finger, just keeps you from reaching up further. Hardware remap is always better so you can take your keyboard with you.

* **Don't burn bad habits into muscle memory**

Remapping `jk` or something to escape is not something you should do if you want to be fast on *any* UNIX system. That only works with Vim.
