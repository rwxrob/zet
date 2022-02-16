# Stop Using `sed -i` in Production Scripts

```
sed: -I or -i may not be used with stdin
sed: -I or -i may not be used with stdin
```

This is what happens when a production script uses the non-POSIX `sed
-i` and that script is run on a UNIX system, whether it be AIX or just
a Mac laptop. Use `perl -i` instead, which always works, or better yet,
don't use shell at all.

    #linux #unix #rants #sed #coding #scripting
