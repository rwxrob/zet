# Add -f to curl when wanting to run the remote download

Just noticed the following `curl` command for goreleaser that allows it to be downloaded, checked, and run in one command:

```sh
curl -sfL https://goreleaser.com/static/run | bash
```
