# Don't Forget to .gitignore go.work

At first I thought I would want this thing around, but it makes is
nearly impossible for others to build from your package if they have it
locally cloned, and for good reason. It's for overriding deps with local
copies.
