# Go embed.FS Changes Perms

After a quick test I learned that adding anything to `embed.FS` with Go
automatically changes the perms to 444 (read-only) even if they had
different perms on the host file system from which they were derived.
This means that embedding any executable will have to have its
permissions changed after extracting from the embedded file system.

```
  1445265      4 drwxrwxr-x   3 rwxrob   rwxrob       4096 Jul 31 15:20 testdata/testfs
  1445269      4 -rw-------   1 rwxrob   rwxrob          7 Jul 31 15:20 testdata/testfs/.secret
  1445268      4 -rwxrwxr-x   1 rwxrob   rwxrob         29 Jul 31 15:19 testdata/testfs/foo
  1445270      4 -rw-rw-r--   1 rwxrob   rwxrob         10 Jul 31 15:20 testdata/testfs/_notignored
  1445266      4 drwxrwxr-x   2 rwxrob   rwxrob       4096 Jul 31 15:19 testdata/testfs/dir
  1445267      4 -rw-rw-r--   1 rwxrob   rwxrob         21 Jul 31 15:19 testdata/testfs/dir/README.md
```

And a simple test on the `foo` file reveals the new permissions.

```golang
//go:embed testdata/testfs
var testfs embed.FS

func ExampleExtractEmbed() {

	foo, err := testfs.Open("testdata/testfs/foo")
	if err != nil {
		fmt.Println(err)
	}
	info, err := foo.Stat()
	if err != nil {
		fmt.Println(err)
	}
	fmt.Println(info.Mode())

	// Output:
	// -r--r--r--
}
```

In other words, `embed.FS` is *not* `tar`.
