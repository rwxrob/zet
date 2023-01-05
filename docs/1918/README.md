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

Creating a webhook that ties to desktop is so easy with this.

Because I'm doing everything from a VM being hosted by a Windows machine I had to make sure to add the following (or something like it) to the configuration file (`ngrok config check` or `edit` to find it):

```
web_addr: http://198.19.1.13:4040
```

* Accepting Github Webhooks with Go · groob.io  
  <http://groob.io/tutorial/go-github-webhook/>
