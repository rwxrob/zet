# Don't create open `openssl.cnf` files, use one in `/etc/ssl`

After going through a tutorial for creating certificates with `openssl` (for bitwarden which I later learned was to use openssl on a Windows machine) I later discovered the gist below that leverages the exising `/etc/ssl/openssl.cnf` file on Linux to save all the error-prone hassle of creating one's own extensions when only the addtional extension is actually needed to create the custom CSR for specific certificate request.

This seems supremely better because I'm not growing-my-own extensions and instead using established extension names that the OpenSSL on Linux project has created.

Related:

* <https://gist.github.com/fntlnz/cf14feb5a46b2eda428e000157447309>
