# Validate a TLS certificate (`.crt`) was created with same `.key`

Recently was asked to update the Harbor certificate and given a `some.crt` file without a `some.key` file. Normally, these two files are created together. But in this case the person sending me the certificate file used the same Certificate Signing Request `some.csr' and therefore didn't sent the `some.key` file since it was the same. When in doubt, the following can be used to compare the modulus value of both to ensure they go together.

```sh
openssl x509 -noout -modulus -in /tmp/some.crt
openssl rsa -noout -modulus -in /tmp/some.key
```

Just have to confirm visually that the two outputs are identical.

Source:

* Verify the Integrity of an SSL/TLS certificate and Private Key Pair  
  <https://knowledge.digicert.com/solution/SO29559.html>
