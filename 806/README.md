# Use fallocate to Create Files of Specific Size

To make a file that is 2 GB in size.

```
fallocate -l $((2*1024*1024*1024)) 2gbfile
```

