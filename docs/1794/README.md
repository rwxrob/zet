# 🤦Use `export no_proxy` to turn off `HTTPS_PROXY` etc.

```sh
export no_proxy="localhost,127.0.0.1,localaddress,.localdomain.com"
```

TIL that `no_proxy` exists. I can't believe how long I have been doing this shit and not known about that. It is even recognized quietly by the Go `net/http` package as well as `curl` and `wget` and pretty much everything else, even though there is absolutely no standard anywhere to be found documenting it.

Why do you care?

Because if your work requires you to have `HTTPS_PROXY`/`https_proxy`/`HTTP_PROXY`/`http_proxy` then having `no_proxy` means you don't have to keep setting and unset them. Just add all your internal stuff to `no_proxy` and you're done.

* proxy - How to use no\_proxy on Linux machines - wildcards, leading dots - Stack Overflow  
  <https://stackoverflow.com/questions/62632642/how-to-use-no-proxy-on-linux-machines-wildcards-leading-dots>
