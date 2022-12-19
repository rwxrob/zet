# Use Go `panic` instead of `log.Fatal`

Noticed that `log.Fatal` does some magic that gets in the way of testing while just a regular `panic` does not, allowing a proper recovery to be written in the test code.
