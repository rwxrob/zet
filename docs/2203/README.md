# Just discovered the golang `time/rate` package for rate limiting

Looks like this "extra" package got a bump in tag to an official number and it getting use out there. Might be worth a look to add rate limiting to platform engineering API development projects.

```
package rate // import "golang.org/x/time/rate"

Package rate provides a rate limiter.

const Inf = Limit(math.MaxFloat64)
const InfDuration = time.Duration(math.MaxInt64)
type Limit float64
    func Every(interval time.Duration) Limit
type Limiter struct{ ... }
    func NewLimiter(r Limit, b int) *Limiter
type Reservation struct{ ... }
type Sometimes struct{ ... }
```
