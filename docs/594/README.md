# Preferred Git Branch Naming Conventions

There appears to be a lot of advice and "best practice" recommendations
when it comes to Git branch naming conventions. So much of it has to do
with the repo and the organization. For example, a massive mono-repo
would need very comprehensive naming conventions to keep track of all
the simultaneous work going on and who is doing it, whereas a small,
personal repo might only need to refer to the issue.

Since I prefer smaller, composable repos (the UNIX philosophy applied to
Git management) my conventions are rather simple:

* Consolidate related issues as needed into single issue
* Create a branch for a single issue (thread)
* Start all branch names with the issue number and a dash
* Names must be readable ASCII identifiers
* Names must match ERE `^([0-9]+)-([a-z0-9-]{5,20})$`
* Main branch always called `main` (less typing)

## Related Code

* `git config --global init.defaultBranch main`
