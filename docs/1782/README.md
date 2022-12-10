# Creating a git branch both remotely and locally

First, create a local branch.

```
git checkout -b <new-branch-name> [<from-branch-name>]
```

Work on it and then push it like anything else.

```
git push -u origin <branch-name>
```

Then, people can use your branch by fetching and checking out.

```
git fetch
git checkout <branch-name>
```

* How to Create a Remote Branch in Git  
  <https://www.w3docs.com/snippets/git/how-to-create-a-remote-branch-in-git.html>
