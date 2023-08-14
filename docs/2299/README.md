# No longer need to create seed in Golang for random

Turns out GPT is wrong about getting a random number (and based on old info, so expected):

> Note that it is necessary to initialize the random seed before generating random numbers. In this case, the `time.Now().Unix()` function is used as the seed, which ensures that a different random number is generated each time the program is run.

As of Go 1.20 (which has been out more than a year) there is no need to create a random seed:

```golang
// return number [0,5)
n := rand.Intn(5)
```

