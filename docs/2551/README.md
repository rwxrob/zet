# Syncing Cobra Version with GitHub tagged version

By putting something like the following in the `build.yaml` file for the Go build action the tag can be automatically incorporated.

```sh
go build -ldflags "-X main.Version=${GITHUB_REF_NAME} -X main.BuiltBy=github-actions" main.go
```
