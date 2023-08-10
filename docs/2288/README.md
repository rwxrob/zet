# Standard argument signature for new Go constructor

As much as I fucking hate it, this is popping up all over as the default convention for creating a generic constructor that has side-effects that involve concurrency or some other middleware-like-thing:

```go
func NewApp(ctx context.Context, config *Config, opts ...option.ClientOption) (*App, error) {
  ...
}
```

I fucking HATE functional options, but it doesn't matter. That is what people use.

I fucking HATE stuttering in every fucking function that uses `context.Context` but they shut my suggestion for `context.C` (or something) down.

And of course, what better way to not commit to shit than to throw a `*Config` in there.

Posts like this don't make me any friends, but I don't give a shit. This is a *horrible* design and I don't care what people think of me. It took an extreme level of over-engineered stupidity to come up with this shit, then again, it's from Google, so of course. Smart people make horrible code all the fucking time.
