# Use `kubectl get ns -l '!name'` to Select No Label

Using the `-l` (short form of `--selector`) with the negation `!` makes
it easy to select things that don't have that specific label.
