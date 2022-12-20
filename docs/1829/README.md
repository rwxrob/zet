# Pretty sure Go 1.18 generics break code coverage

Here's the coverage script:

```bash
#!/usr/bin/env bash
go test -coverprofile=/tmp/cover
go tool cover -html=/tmp/cover -o /tmp/cover.html
perl -e 'local $/; open $fh,"<", $ARGV[0]; $buf=<$fh>; $buf=~s,<span\s+class="cov0"[^>]+>([^<]+)</span>,<b>\1</b>,gms; print $buf' /tmp/cover.html >/tmp/cover-lynx.html
lynx /tmp/cover-lynx.html
rm /tmp/cover*
```

The above works fine on everything but the rather hairy use of generics below:

```go
func keys[M ~map[K]T, T any, K comparable](in M) []K {
	seen := map[K]bool{}
	for k, _ := range in {
		seen[k] = true
	}
	keys := []K{}
	for k, _ := range seen {
		keys = append(keys, k)
	}
	return keys
}
```

The following unit test should cover it, but doesn't:

```go
func ExampleKeys(t *testing.T) {
	it := map[string]bool{
		`one`:   true,
		`two`:   true,
		`three`: true,
	}
	for _, v := range keys(it) {
		fmt.Println(v)
	}
	// Unordered Output:
	// one
	// two
	// three
}
```

This is rather annoying.
