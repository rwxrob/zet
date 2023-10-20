# Beauty of `gh issue develop -c`

Since discovering `gh issue develop -c` I never do anything else when working on a PR. The workflow is just so wonderful:

## Open or update an issue related to the specific work to be done

```sh
gh issue create
```

## Create a branch and check it out for the work

```sh
gh issue develop -c NUM
```

## Commit each small logical change and push to branch

```sh
git commit ...
git push
```

## Create a PR and add reviewer(s)

```sh
gh pr create
```

## Close the PR with a "squash and merge" after review

```sh
gh pr close
```
