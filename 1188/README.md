# Problem with Perl, It's Too Damn Good

The only *real* problem Perl has faced over the years is that it is just
too fucking good at what it is designed to do: rapid application
development. It is secure, robust, wicked fast to write, easy to
document, and has just enough object-oriented stuff (which really isn't
OOP and more like Go) to make it very powerful. All this creates the
single biggest problem: Perl does just enough and keeps on doing just
enough. 

People cannot justify redoing their projects in other languages like
Python (not much better) or Java (HELL no) or even Go. So all that Perl
code just keeps on running out there. There are 10s of thousands of
lines of Perl at my current workplace that people are still completely
unmotivated to touch, and why should they, it just works. 

Perl's age has nothing to do with its quality. Remember this is a *shell
scripting language* primarily designed to replace `sed`, `awk`, `tr` and
`cut` and yet has become the international standard for regular
expressions. That's all Perl is, it's not an enterprise programming
platform and never was, despite what all the brain-dead people did with
MOOSE and all the rest, including my own `classes` pragma. 

In fact, CPAN was largely a huge fucking mistake even though people cite
it as an advantage all the time. Python and Rust and Node have all shown
us the huge fucking mistake it is to have a massive "registry" (and in
Node's case) without any checksumming at all. This directly influenced
the brilliant decisions behind Go to have *no registry at all* and use
Git repos (supplemented with controlled caching servers) instead, that
are already secured and checksummed. (I would pick Go over ever other
alternative just for that fact alone.) No, Perl's CPAN was a mistake.

Keeping Perl small and using it as a `sed`/`awk` replacement was always
the plan and is still one of the best uses and best kept secrets in the
IT world. Unfortunately, this means your Perl prototype must not stay
that way for long because no one else can read it and won't because of
seriously dumb-shit stigma against it. I did a [video] on this as well.
And that is Perl's biggest problem, you just won't ever rewrite your
prototype because it just works and you are on to another "just works"
project before you ever get a chance to circle back. That is what got
Perl into trouble and will get you into trouble today if you fall victim
to it like the rest of the world has for the last two decades. It's
largely the "interpreter mania" that took over the whole world and
Perl's not the only one to blame there, but it did start the whole
thing. "Humm, C, POSIX shell, or Perl? Which one will I use to rapidly
develop this 90s web back end?" You know what the answer was. Just learn
from those bad mistakes and don't make them again.

[video]: <https://youtu.be/AGoLnnOFBoc>
