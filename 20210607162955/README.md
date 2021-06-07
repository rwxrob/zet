# Stop Annoying Kubernetes Messages About "Throttling"

Recently, we upgraded our version of Kubernetes and started getting a 
ton of stuff that would write to standard error output beginning with 
codes like I0601 and would contain some reference to throttling. The
new throttling is good and all, but these messages are freaking 
annoying. Redirecting them to /dev/null would silence other potential
problems. But a good friend and colleague of mine at work discovered 
that changing the permissions on ~/.kube/cache removes the errors.

```
chmod 755 ~/.kube/cache
```

I have no idea why this stops the messages, but it does. I’ve confirmed
it with two people, and it’s nothing that would break anything.
