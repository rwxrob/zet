# TIL What a Sparse File is

Sometimes a file doesn't actually take it's size in disk space. Very
weird.

```
$ ls -hl /tmp/okteto-test
total 4.0K
-rw-r--r-- 1 rwxrob rwxrob 5.0G Oct 29 00:02 5g.img
-rw-r--r-- 1 rwxrob rwxrob 5.0G Oct 29 00:02 another5g.img
-rw------- 1 rwxrob rwxrob  232 Oct 28 23:19 okteto.yml

$ du -h /tmp/okteto-test
12K	/tmp/okteto-test
```


* Sparse file - Wikipedia  
  https://en.wikipedia.org/wiki/Sparse_file
