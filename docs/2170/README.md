# Use openssl rand to generate random text data

Since `openssl` is on most things and `${RANDOM%23}` doesn't alwasy cover the need, you can use `openssl` to generate completely random text from hexidecimal values.

```sh
openssl rand -out foo -hex 100
```
