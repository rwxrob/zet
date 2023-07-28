# Use goreleaser and gh release upload to create releases

It's always better to use a GitHub action, but when you cannot you can use the `goreleaser` and `gh` binaries to greatly reduce the work involved.

```sh
goreleaser --snapshot --clean
git tag -f v0.1.0 && git push -f origin v0.1.0
gh release create v0.1.0
gh release upload v0.1.0 dist/*{Darwin,Windows,Linux}*
```
