# Provide own customized schemas to vim

Saw this line at the end of the sample `goreleaser.yaml` file. It appears that the Vim LSP is capable of pulling in schemas over the internet from URL sources that can be saved into the files themselves.


```yaml
# The lines beneath this are called `modelines`. See `:help modeline`
# Feel free to remove those if you don't want/use them.
# yaml-language-server: $schema=https://goreleaser.com/static/schema.json
# vim: set ts=2 sw=2 tw=0 fo=cnqoj
```
