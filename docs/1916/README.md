# Creating a minimal Go webhooks server

Because I'm doing everything from a VM being hosted by a Windows machine I had to make sure to add the following (or something like it) to the configuration file (`ngrok config check` or `edit` to find it):

```
web_addr: http://198.19.1.13:4040
```

* Webhook receiver for GitHub, Bitbucket, GitLab, Gogs  
  <https://golangexample.com/webhook-receiver-for-github-bitbucket-gitlab-gogs/>
* Accepting Github Webhooks with Go · groob.io  
  <http://groob.io/tutorial/go-github-webhook/>
* ngrok - Online in One Line  
  <https://ngrok.com/>
* localhost - How to change ngrok\'s web interface port address (not 4040)? - Stack Overflow  
  <https://stackoverflow.com/questions/36018375/how-to-change-ngroks-web-interface-port-address-not-4040>
