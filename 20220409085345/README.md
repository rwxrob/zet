# Don't Be a GetOpt Diseased Zombie, Code Better

I fucking hate what GetOpt has done to the otherwise elegant UNIX
command line interface. Just look at `gpg` for an example of how fucking
horrible that dash hell has become. Why? Why did we allow it to get that
bad. We had a very functional (UNIX filters) approach from the very
beginning and monoliths like `gpg` violated it in the worst possible
way.

We have an opportunity to rethink human-computer interactions from the
command line, and guess what, applying the same tenets of good
programming apply. This is why Bonzai effectively forces developers to
think more about how their tools are going to be used. To think in ways
that are consistent with their thinking when they are actually writing
code.

For example, consider the hypothetical Go function:

```go
func Foo(whatever ...any) {
   // ...
}
```

Now imagine passing something like this to it:

```go
Foo("--dry-run", "-n", "mynamespace", "--output=json")
```

Now imagine the code to process that? It takes a full fucking language
scanner and parser just to process what should have been a simple set of
parameters. This is why Cobra and even Flags code is so fucking ugly.
All because `getopt` fucked us all. Make no mistake, `getopt` is a full
language all by itself, some monstrous dark grammar that was forced onto
a very practical world of simpler interfaces.

KEEP YOUR FUCKING LANGUAGE OFF MY COMMAND LINE!

I get very angry when I think about it. No sane programmer would ever
allow one of their peers to create a function like `Foo`. "But I want it
to be flexible" would get you laughed out of the room (or fired). It's
fucking idiotic to make it that broad and non-specific. IT'S THE
ANTITHESIS OF GOOD CODING! But, somehow everyone thinks that this
insanity is somehow okay when it happens on a command line for a single
command. Because the standard for communication and interactions with
HUMANS on the command line has been so abused by "not only humans use the command
line" that we get toxic monsters like `gpg`.

The command line was created for humans. Somehow we really forgot this.
But, I never forgot, and I'm going to champion command line interactions
for humans, without having to give up anything until the day that I die.
And I'm not the only one, TJ Holowaychuk agrees (in his own way).

Here's that exact same thing done more sanely:

```golang
var dryrun bool
var namespace,output string

func Foo() {
   // ...
}

// and we would run it

dryrun = true              // step 1
namespace = "mynamespace"  // step 2
output = "json"            // step 3
Foo()                      // step 4

```

Not very functional, but neither was the other monstrosity. Another way
would be to set all of those up front and then pass them into the Foo
function. The point is, there are a number of specific, clear steps that
change state. This doesn't jam them all into a single fucking line
without knowing which has priority, what if something is repeated, and
all that. THAT is how we should think of humans interacting with the
shell.

After all, every line on the shell is a line of an ongoing program. So
why have a double standard for interactive users who are writing code as
they go? Interacting with the shell is coding.

"But what if they want `--private`?"

Think like a *good* coder. What would a coder do? Have them set a
variable that is observed by the function, or pass a consistent
parameter to the function itself.

Technically, we have this with environment variables. In fact, one of
the most brilliant decisions ever made from the Go team was `GOOS` and
`GOARCH` which are provided *before* calling `go build`. You can't even
set them from the command line with dashes at all. You *must* use the
stateful environment variables. That is good design. You can change the
state for your one execution, or you can keep it on for all your
executions. We need more of that, not less.

Another positive move in the right direction is `kubectl` contexts. You
can save different states, which are effectively combinations of
arguments that would otherwise be on the command line. You just change
your state and all your simple command line interactions use that
context. Humans are stateful beings. It's how we communicate. And it
also doesn't stop our programs from using the same interfaces. Anything
a human can do on the command line, so can a program.

Besides, why not look at the command line as a language? By banishing
`getopt` and those horrible dashes, we also promote the creation of our
own, human-friendly domain-specific languages. Remember, `getopt` is a
language, a fucking horrible language. People freak out by allowing
several arguments on the parameter list to be interpreted differently,
but it is rather easy, and human friendly, because we do it all the
time. Don't believe me? How about believing the creator of Express,
Stylus, Jade/PUG, and Apex, TJ himself. Look at his Apex log tool and
how he created a domain-specific language rather than a horrible getopt
monstrosity. TJ is *obsessed* with good design. His code base is one of
the most beautiful things I've ever seek. He's a creative, a
photographer, and a crafter of very fine code. He gives a shit about
user interactions. He gets it. He understands, and he makes things that
don't have complicated interfaces with dashes.

So have the courage to give up your deformed babies, pot-marked with
pustule dashes all over their faces. Think differently about how you
would do that entire user interaction. How would you code it? I promise
you will find a better way. You'll find it if you remember to think like
a programmer about the command line, and not some exceptional thing that
requires every fucking thing be done on a single line (without pipes).

    #rant #bonzai #cleancode #coding #programming
