# Created a release for my personal `z` command

It's about time. People can now simply download my personal `z` Bonzai stateful command tree monolith to play around with to get an idea of how it works.

```
curl -L https://github.com/rwxrob/z/releases/latest/download/z-linux-amd64 -o rwxrobz
```

I also added the following details about creating a release. It's wicked simple now.

```
z go build
gh release create
gh release upload TAGVER build/*
```

Looking forward to getting feedback on it.
