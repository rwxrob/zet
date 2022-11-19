# Go Template FuncMap Pipe to Functions Goes to Args

TL:DR; `{{ some | myfunc }}` sets the output of `some` to the *last*
argument of `myfunc`. If I have more arguments to `myfunc` they come
first, which means that `args[len(args)-1]` will always be the piped
input.

I swear this isn't documented anywhere. Spent a good hour looking
through all the official docs and then finally gave up and looked at the
Hugo source code at their `jsonify` and figured it out. I cannot stress
enough how important it is to be able to clone and read source code
quickly to get the fastest resolution to your problems. The *tough*
questions are almost never answered in documentation on the web.
Mediocre developers love flooding the Web with shitting simple
tutorials, just nothing about these tough questions, which is really too
bad.

By the way, Go templates are *tremendously* powerful. The most
intelligently created templating system I have ever experienced. I would
pick Go just for the templating system alone, it's that fucking good.
It's also the reason you don't need a fucking "framework" to do Go
development of any kind. Just use Go. Rob Pike is a fucking genius. (Be
sure to watch his hour long video on creating the scanner/parser for the
Go template engine.)

    #golang #coding #tips #templates #functions #FuncMap
