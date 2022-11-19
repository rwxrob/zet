# Setup HTTP Proxy with Git

Apparently, all that is needed is a global configuration that uses
`http.proxy` and/or `https.proxy`.

```
git config --global http.proxy http://whatever.example.com
git config --global https.proxy http://whatever.example.com
```

    #git #httpproxy #tips
