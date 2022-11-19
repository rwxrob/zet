# Safe POSIX Shell Script `read` Idiom

I've long known all the different forms to send input properly to a
`read` loop in Bash, but POSIX is not so obvious. This is because POSIX
lacks the `<<<` and `<()` and `< $()` other variations. Here's how to do
it correctly:

```
IFS= read -r line << EOF
$(foo)
EOF
```

