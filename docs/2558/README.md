# Sometimes you want to tell git exactly how to use ssh

Usually, people will want to let `git` use their configurations for ssh (usually in `~/.ssh`) but sometimes so much is customized in an automation that taking over the entire brain of `git` for all `ssh` things is easier.

```sh
GIT_SSH_COMMAND="ssh -i ~/.ssh/id_rsa -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=n
o"
```


