# One reason to use home kit instead of scripts collection

I absolutely hate `#!/usr/bin/env whatever` yet this is the only way to get any interpreted script to work on everything (thanks Apple). It's also extremely insecure. There was a time when such things were not allowed on UNIX systems because of `PATH` injection attacks.

Guess what? None of that is relevant with a home/root kit monolith approach that Bonzai facilitates, even more reason to use it.
