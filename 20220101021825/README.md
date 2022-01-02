# Things to Learn in 2022 to Get Best Tech Jobs

0.  Becoming an autodidact
1.  Linux bash command line
2.  Git and GitHub
3.  Networking essentials
4.  Containers and Kubernetes
5.  Programming in Python, Go, Javascript
6.  Fundamentals of machine learning
7.  Managing and sharing your knowledge
8.  Security as a mindset
9.  Manage your career search

Other less technical but relevant skills:

*  Working remotely
*  Managing you money
*  General statistics
*  Motivating yourself and others
*  Communicating with influence
*  Unleashing your creativity
*  Connecting with your tribe

## Linux bash command line

Linux (which evolved from UNIX) is *the* tool for the most important
jobs of 2022. Even though UNIX dates back to the 70s, learning to break
even common problems and utilities into composable bash scripts like a
UNIX boomer could be the best change in mindset you'll achieve in the
new year. Your productivity will increase in ways you cannot foresee and
you will appear to be using magic to those stuck using graphics user
interfaces.

You can't see it, but UNIX and Linux are the underlying operating
systems on almost every device in the world including your phone and
pretty much every web site you have ever visited. This is why the
fastest growing and highest paying jobs currently require at least
fundamental knowledge of the Linux bash command line. The better you
get, the more you will outshine every other candidate for any tech job. 

Why bash shell specifically?

*Bash is the most important programming language you will ever learn.*
Every line you type on the command line *is* programming, in bash.
Combine several of those lines together into a file and you have a
script. Unlike other programming languages bash empowers everything you
do every time you use the command line, including coding in other
languages. It is not enough to know how to code, bash command line
skills allow you to test, deliver, and share your code by connecting and
automating with other tools.

Learning the bash command line also specifically includes a strong
understanding of the UNIX philosophy and use of filters, programs that
accept input, transform or operate on it, and produce output. Mastering
this approach allows reuse of filter utility scripts by chaining them
together into pipelines and even using pipelines within your
command-line text editor to write code that writes for you. 

Bash is the default shell on 90% of Linux systems. It is also the safest
shell in existence. Bash also happens to be the most powerful shell you
can learn doing things that no other shell can (including completion and
pretty prompts that are popular with users of other shells). Learning
`shellcheck` with Bash ensures you can quickly make POSIX compatible
shell scripts as well when required. 

How do you learn bash?

Read the manual. Seriously, `man bash` is by far the most comprehensive
way to learn it. There is not a book on the planet that covers the
material better. Perhaps start out more simply by researching how to
complete challenges first. But, for this language you should *always* go
to the manual page because there is just too much shit on the Internet
that is just dead wrong, inefficient, and dangerous at worst. 

For example, StackExchange is sites like it are full of unnecessary and
stupid use of `awk`, `sed`, `cut`, `tr` and other subshells. These
"solutions" also frequently use the ancient single bracket conditions
(`[]`) instead of the safe double-bracket alternatives. If you see
single brackets in bash code you know for sure the author had not idea
how to code bash. What's worse, is that often the people posting this
shit are as pretentious as they are clueless. You don't have fight. Just
read the manual page be better and safer and 'always' run any code
through `shellcheck`.

> ⚠️
> POSIX shell scripts are inherently more dangerous and easy to fuck up
> than good bash. The idea that POSIX shell is somehow safer and more
> compatible is simply a myth in 2022 and can easily be objectively
> proven false.

## Networking essentials

"The Network is the computer." (Sun, 1990s, now bankrupt)

Okay, it really isn't (despite the insanity of the latest 90s) but the
network is definitely so important and ubiquitous that understanding how
the Internet actually works is not only mandatory but the more you learn
the more it sets you apart from everyone else in very significant ways.

Kubernetes and containers have upped the complexity and scope of
networking. Once upon a time as a developer you could be good just
understanding the absolute basics. These days you have to be able to
"bridge" container networks just to access stuff on your own local
system. Kubernetes has even more complexity for all the right reasons
that you need to learn if you ever want to deploy your application
cleanly and securely into the cloud, which is everything in 2022.

One of the best ways to learn networking is to setup your own simple
physical home network using used computers or Raspberry Pis and then put
a sniffer on one to inspect all the traffic as it is happening. This
will give you greater than book knowledge about how networks work. Who
knows, you might even catch unauthorized traffic and catch a hacker on
your network (like I did when I first did this).

## Containers and Kubernetes

Want the highest paying, most challenging tech job of 2022? Become a
Cloud Native Infrastructure Engineer. The industry has the "largest tech
skills drought in history" because it cannot fill the roles of cloud
native infrastructure engineers right now where the *median* salary is
146,000 dollars. My friend, a veteran, just landed a job over 300,000 to
help companies setup their on-prem cloud native infrastructure (and I've
been offered over 250,000 as well, even though I took another job for
less).

Docker might have started it, but containers have gone far beyond Docker
at this point. Sure we still use the `docker` command for everything,
but containers are now the fundamental building block of most enterprise
IT infrastructure. *Not* knowing how to use and create containers is a
serious red flag to most IT employers today (although apparently not
enough to stop me from getting a job as an Infrastructure Engineer where
I then learned it).

Like former me, you may be thinking, "I don't need to learn containers,
I just need to learn how to create applications and infrastructure."
Like me, you'd be dead wrong. Modern applications *are* containerized
from the very beginning. If you get a green-field project and don't
think immediately about how that application is going to be deployed
as containers --- most likely into Kubernetes --- then you are just
doing it wrong in 2022. If your current team does not understand the
significance of that or the reason why start looking for another job
today.

Containers and Kubernetes are not just for shitty, insecure NodeJS apps
and "DevOps." (Node is being replaced by Go REST APIs bottled in much
safer, lighter, and faster "FROM SCRATCH" containers, btw.) Containers
and Kubernetes are being used at large scale to deploy high-performance
machine learning model creation, services, and testing. This stuff is
already everywhere and is going to continue to explode in scope more
than it already has. 

## Programming in Go, Python, and Javascript

Okay, I'm not including bash (the most important programming language
you will ever learn) because I already wrote about it. But the next most
important languages to learn in 2022 are Go, Python, and (of course)
JavaScript (which kinda includes HTML and CSS that most would argue are
not *true* programming languages).

Why these three? Mostly, because they are not only in strong demand but
have a very bright future ahead. Let me explain that a bit.

Go was specifically written to address the highly-concurrent, frequently
compiled, performance sensitive requirements of the world's largest
Silicon Valley company, Google. Rob Pike and Ken Thompson brought the
world C, UNIX, Unicode, Plan 9 and several other things as well as the
Go programming language, which they call "a modern C". Every major
application and tool in the cloud native landscape is written in Go,
most importantly Docker and Kubernetes. Most companies are actively
replacing legacy code in NodeJS and Java with Go. Here's one statement
from a relatively small but important modern company like Uber:

>  "While historically Uber has been mostly a Node.js and Python shop,
>  the Go language is becoming the language of choice for building many
>  of Uber Engineering’s new services. There is a lot of momentum behind
>  Go at Uber, so if you’re passionate about Go as an expert or a
>  beginner, we are hiring Go developers. Oh, the places you’ll Go!"
>  (2016 )

Go static typing fulfills the needs of most large projects better than
any interpreted language (yes even TypeScript) and cross-compilation
makes is flexible for everything including ultra-lightweight "FROM
SCRATCH" containers that require a compiled language. Go's batteries
included selection of network and encryption modules --- not to mention
gRPC and ProtoBuf --- make it the dominant pick for cloud native
applications development as well. Even if you just want to work in cloud
native operations learning to read Go will help you understand what the
applications are doing when the documentation fails you. For example, by
reading the source code of `kubeadm` you can get a perfect understanding
of every step necessary to create a Kubernetes cluster.

Python's greatest contribution to the world is a really kick-ass C stub
and encapsulation framework. People write simple Python code, then when
they come to stuff that needs improvement, they write C code and create
a stubbed library module to import. This is why Python gets all the
credit for the innovations of PyTorch, Tensorflow, NumPy, SciPy, Pandas,
and other C code masquerading as Python. Python also includes a full
version of SQLite (simple database) and TK (for graphics). Even though
Python suffers from serious distribution issues (and always has) it is
still mandatory learning for anything involving numbers, math, machine
learning, systems automation, and cybersecurity.

## Fundamentals of machine learning

## Managing and sharing your knowledge

## Security as a mindset

## Becoming an autodidact

## Working remotely

## Managing you money

## Motivating yourself and others

## Communicating with influence

## Unleashing your creativity

## Connecting with your tribe

Related:

* <https://github.com/rwxrob/boost>
