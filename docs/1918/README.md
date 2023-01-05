# ngrok.io looks amazing!

Ingress-as-a-service is what they are calling it, and I cannot say how amazing I think this is. I first noticed this in a tutorial about how to setup your own webhook server on the Internet without exposing an entire server to the public.

Created an install script:

```
#!/bin/bash
set -x
curl -SsLO "https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz"
mkdir -p ~/.local/bin
tar zxvf ngrok-v3-stable-linux-amd64.tgz -C ~/.local/bin
```

* Accepting Github Webhooks with Go · groob.io  
  <http://groob.io/tutorial/go-github-webhook/>
