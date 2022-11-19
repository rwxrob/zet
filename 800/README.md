# JSON Path and Go Templates Mandatory Learning

I might not like JSON Path (compared to `jq`) but you never know when
you are not going to have `jq` around. So learning JSON Path is really
mandatory to do anything with `kubectl`. Thankfully, this is almost
identical to `jq`:

```
$ k get pods -o jsonpath="{.items[].metadata.name}"
```

By the same token, when wanting to create a nice report, or when working
with Helm templates, Go template language is mandatory learning.
