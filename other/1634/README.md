# Specify Go `Init()` Instead of Constructors

I'm reminded of the reason that `Init(...) error` is preferred over
making a constructor function in Go. Init can be specified in an
interface, a constructor cannot. This allows designers to specify what
should happen when one of a thing is first created/initialized when
writing the interface specification. It also allows anything that
implements Init to re-initialize without losing the underlying reference
to the same thing being initialized. This is usually preferable to
destroying it and making a new one --- especially since stuff out there
might already be using that previously create reference.

    #golang #tips #coding
