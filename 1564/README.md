# Go embed Files Can Be Too Large

```
$ go build -o foo
# github.com/rwxrob/lab/go/embed
./main.go:11:5: embed 2gbfile: file too large (2147483648 bytes > 2000000000 bytes)
```

