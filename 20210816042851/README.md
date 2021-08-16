# Use Single Quoted Argument with `watch`

Most admins and hackers know about `watch`. It's the fastest way to turn
a TMUX pane into a powerful dashboard monitor module by running its
arguments in a loop. But what some may not realize is that you actually
can use pipes and subshells as long as you wrap the entire thing in
single quotes so that it appears as a single argument to `watch`.

```bash
watch -n 5 'k get node myk8snode -o json | jq .metadata.labels |grep
nvidia'
```
    #linux #watch #tips #secops #hacking #tools
