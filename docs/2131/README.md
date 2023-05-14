# Use truncate to create files of a specific size

This is an ideal way to start a file to eventually contain an ext4 (or other) filesystem for use with Amazon Firecracker (or other VM engine).

```
truncate --size=100M myfs.img
```
