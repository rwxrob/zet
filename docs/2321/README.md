# First impressions of log/slog in Go

So happy with the tough design decisions from the `log/slog` team in order to preserve simplicity for beginning Go programmers (and all Go programmers) over the completely brain-dead alternatives. Functional arguments (which can never be persisted) are one of the stupidest things ever forced on Go programmers by people who don't have to use their APIs and applications.

## Warning

Stay the hell away from this blog that promotes over-engineered functional arguments (while simple arguments are the default):

<https://betterstack.com/community/guides/logging/logging-in-go/>

