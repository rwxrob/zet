# Make Speakable Command Line Interfaces

It's 2021. People use their phone for everything. The Google Pixel now
just lets you double tap the main button to pull up the voice
interface. No one is thumbing shit into their phone interfaces unless
they have to. This is the age of the conversational user interface, of
assistants that listen to us constantly and (finally) do what we want.
Gone are the constraints of terimal input (even though terminal input is
just text). Gone are shitty menu-driven graphic interfaces. It's
a speakable, search-centric world. Thank God! It's about time.

And yet, for some dumb-ass reason we continue to complicate command
options with dashes and stuff no speech processor would ever understand. 

The only thing that distinguishes a terminal command line from
a voice-able user interface is the ability to generate text from speech
(which every phone and computer provides these days) and the developer
design decision to create speech-friendly command line interfaces. This
is why *knowingly* creating any interface in 2021 that requires dashes
and obscure letters and unpronoucable underscores is just so fucking
stupid.

It's just a matter of time before the world wakes up and gets tired of
translating speech commands (from Slack bots, for example, which have
sales people using the command line without even knowing it) into their
bullshit horrible dash and double-dash equivalents. This is the reason
Cobra is such shit. It *promotes* these ancient ways of interacting with
the computer via the command line.

The tragety is that these `gpg`-like monstrosities came about because of
constraints of the computer and terminal interface from the 70s.  A lot
of good things came from the 70s, cryptic, unintelligible command line
application interfaces were not one of them. Someone decided --- quite
arbitrarily --- that the world would forever suffer from dash-syndrome
and we have paid for it ever since. The `man` page is literally
a response to the dumb-ass decision to make interfaces as
counter-intuitive as possible. 

This shit needs to fucking die. The word needs software developers and
designers to have to courage to stand up and say, "No. This sucks. No
one will remember this." 

Linus Torvalds was one of the first with `git`. He had the courage to
buck tradition and put *several* applications into a single monolith
while maintaining the spirit of the UNIX philosophy to "do one thing
well and have it integrate." He just didn't have the courage to say how
shitty dashed options are, because he is an engineer. His decision has
spawned the new normal for monolith utility applications such as
`docker`, `kubectl` and a host of others. He made it okay because he had
the courage to say, no more.

We need that same thing now, but with the *rest* of the command line. We
need courages software utility designers to set the bar very high with
design policies that dictate, "There will be nothing in our interface
that could not be spoken into a Slack bot."

Engineers gave us HTML, a complete disaster. Writers gave us Markdown in
response. We need more tech people with writer-mentality creating
software that caters to everyone, not just those who can memorize which
fucking dash option is needed.

    #coding #developers #design #cli #terminal #tips #linux #secops
