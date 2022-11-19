# Zsh is Shit: Unnecessary Zsh Completion Complexity

More evidence that Zsh is just pure shit. I know Bash is bloated and has
its own problems, but after a quick read of the completion system for
Zsh with all its unnecessary complexity missing the plain and simple
idea of `complete -C foo foo` from Bash I'm convinced the creators were
too intelligent to make anything useful. It's a fucking mess. In Bash
all I have to tell someone is to add one line to enable completion to be
done by the program that needs the completion. In Zsh you have to source
this and that external function, and `autoload` this other thing, all
because the Zsh designers were just fucking clueless from the start. No
wonder Bash remains the default on all modern Linux systems that have
enough room for it (containers, of course, use BusyBox `sh`). In fact,
Zsh's completion design is so *fucking* brain dead that I refuse to ever
support it in CmdBox. People can fork the project if they want it. I am
just never going to legitimize that absolute shit, not with anything
under my control at least. That's what FOSS is all about. Doing what you
want.
