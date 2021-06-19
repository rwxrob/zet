# Inferred Completion from Usage is Idiotic

I'm sick and tired of reading all the write ups claiming that Zsh
completion and Fish are "superior" to Bash and the rest because they are
good at guessing the completion from the usage documentation full of
shitty dashed options and impossible to speak or remember parameters. It
is *not* the shells job to do your completion for you. It is the job of
the *program* itself, and always has been. 

Thing about how fragile that completion system is. It is 100% dependent
on people agreeing about the "standard" for parameters, options, and
usage documentation. Sure you *can* creation your own completion, but it
has to be written in a separate program and placed carefully into the
system that Zsh controls. You have to have an entire fucking package
installer just to get completion on the system with your simple utility.
That's just stupid, really stupid. All that work should not only be
allowed and supported in the programs themselves, but preferred and
encouraged. IT IS THE FUCKING PROGRAM'S JOB TO DO ITS OWN COMPLETION!

I'm probably the only person on planet Earth who feels this way at this
point. Everyone has bought into this fucking insanity. But I just don't
give a shit. The status quo for command line UX is fucking horrible and
needs to die the death it has deserved for more than a decade. The age
of speakable, intelligent command line interfaces where the commands are
responsible for their own completion and documentation is the way of the
future and present. I've never wanted CmdBox to be completed more.

Don't get mad. Get busy.
