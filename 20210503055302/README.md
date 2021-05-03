# Git Notes

Recipes and such for Git source management system.

## Mandatory Git Reading

* `man gitutorial`
* `man giteverday`
* `man git`
* `man gitcli`
* Git User's Manual
* <https://chris.beams.io/posts/git-commit/>

## Different Uses for Git

People approach Git with different needs. I believe it is very important
to keep this is mind when helping others learn it. Three fundamental
differences for me are as follows:

1. Publishing written content with Git (just knowledge source)
1. Sandbox quick-n-dirty projects (sometimes gits fall into this)
1. Formal source code management

## Git Master Levels

1. No Git at all. 
1. Uses Git behind another script or tool. 
1. Understand content states and basic commands.
1. Branching. Rebasing. Squashing. Merging. Oh my.

## Important Concepts and Observations

* "Git deals with changes (content snapshots) not files"
* index, cache, and staged are synonyms
* "If applied, this commit will ..."
* "the `--patch` flag should be top of the git manual"
* "staging/cache/index is global state, does not belong to any branch"

>    kaar One big downside with using tools like GitHub and GitLab  
>          is that a lot of information about the code is getting    
>          lost in PullRequest/MergeRequest. Information that should 
>          go into you commit messages. GitHub/GitLab issues and prs 
>          and comments are lost and hard to migrate                 

## Individual Learning Plan

Tasks I want to upgrade:

* Rebasing (1.5 -> 3)
* Merging  (2 -> 3)
* Branching (2 -> 3)
* Squashing (2 -> 3)
* Versioning (2 -> 3)
* Stashing (2 -> 3)

1. Identify reliable sources of knowledge and training

## Resources

* `man git`
* <https://git-scm.com/>
* <https://youtube.com/c/DanGitschooldude>
* <https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases>
* <https://medium.com/swlh/git-flow-vs-github-flow-3ad44bd46407>
* `tig`
* <https://github.com/googleapis/release-please>

## See Stuff

* `git status`
* `git log [-p]`
* `git show <commit>` 
* `git diff [--cached]`
* `git tag`
* `git ls-remote --tags`

## Add Stuff

```
git add .        (current dir only)
git add -A .     (current dir and all subdirs recursively)
```

## Delete Tags

```sh
git tag -d <tag>
git push origin -d <tag>
```

## "Oh Shit" Recovery

I staged and need to undo it:

```
git reset -p .
```

## List All Remote Tags

```sh
git ls-remote --tags | pae 's,.+/,,'
```

## Create a "Bare" Repo for Local Backups

Some repos have no business being on GitHub or GitLab, but using the
same workflow is nice. I prefer to not even keep this anywhere near my
`$REPOS` directory with everything else.

```
cd # to get home
mkdir priv
cd priv
git init
git init --bare /media/rwxrob/06CF-482C/priv.git
git remote add bak /media/rwxrob/06CF-482C/priv.git
git push --set-upstream bak master
```

And can clone it with the pull path.

```
git clone /media/rwxrob/06CF-482C/priv.git
```

## Show the Exact Staged Content

```
git diff --cached
```

WARNING: `git diff` (for me) is utterly useless. Using `--cached` shows
*exactly* what is staged (when `git diff` without it will show nothing.

## Change First Commit Message

```
git rebase -i --root
```

## Change Last (Unpushed) Commit Message

```
git commit --amend
```

## Change Recent Commit Messages (Besides Last)

Careful on this one. `N` is how far back.

```
git rebase -i HEAD~N
```

## Delete a Branch (Including Remote)

```
git branch -d <name>
git push origin --delete <name>
```

## Change Default Branch for Existing Repo

```
git branch -m master main
git push -u origin main
```

## Changing Default Branch for New Repos

```
git config --global init.defaultBranch main
```

## Push and Delete Branch

```
git push origin :branch-to-delete
```

This works because the colon separates `<from>:<to>` and an empty from
blows away the destination.

## Dangerous Shit

```
git push mirror # omg, i juse blew away all local branches
git push origin :branch-to-delete # deletes remote branch
```
