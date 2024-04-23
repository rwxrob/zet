# Using PAT in GitHub Action for Go private repo builds

Update: Decided against PAT for building Go projects with private repo dependencies with GitHub actions because managing ssh keys is just so much more flexible and easy to setup—especially when storing the ssh key in Vault. Using PAT creates an implicit dependency on GitHub that unnecessarily locks the CI/CD to GitHub that need not be.

----

```yaml
jobs:
  run:
    runs-on: ubuntu-latest
    env:
      GOPRIVATE: github.com/fabianMendez/privatemodule
      GH_ACCESS_TOKEN: ${{ secrets.GH_ACCESS_TOKEN }}
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-go@v2
        with:
            go-version: '1.16'
      - run: git config --global url.https://$GH_ACCESS_TOKEN@github.com/.insteadOf https://github.com/
      - run: go build
om/

```

!!! warning

    DO NOT FORGET THE TRAILING SLASHES IN git config --global LINE!

But what about limited to `url.ssh`?

* How to use private go module in GitHub Actions  
  <https://blog.fabianmendez.dev/how-to-use-private-go-module-in-github-actions>
* github actions and go private modules · Aran Wilkinson  
  <https://aran.dev/posts/github-actions-go-private-modules/>
