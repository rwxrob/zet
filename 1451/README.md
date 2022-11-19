# Force JSON Ansible Output

JSON output does not play nicely with `jq` by default. But it can be
convinced with the following setup changes. Add this to an
`.ansible.cfg` file in the current project directory or your home
directory.

```toml
[defaults]
bin_ansible_callbacks=True
```

Then you will need to add this to your `~/.bashrc`.

```
export ANSIBLE_LOAD_CALLBACK_PLUGINS=1
export ANSIBLE_STDOUT_CALLBACK=json
```

Now the following will work.

```
ansible -i inventory all -m ping > foo.json
jq -r '.plays[].tasks[].hosts | to_entries | .[] | .key + " " + .value.ping ' foo.json
```

This will give you a clean output like the following. Note that the
Ansible JSON plugin designers very poorly choose to use a schema that
requires the conversion `to_entries` to get the name rather than include
it in the object itself (which really needs to be added as an issue
since it's pretty bad).

```
control1 pong
control2 pong
control3 pong
hpz640 pong
mini1 pong
mini10 pong
mini11 pong
mini12 pong
mini13 pong
mini14 pong
mini15 pong
mini16 pong
mini17 pong
mini18 pong
mini19 pong
mini2 pong
mini20 pong
mini3 pong
mini4 pong
mini5 pong
mini6 pong
mini7 pong
mini8 pong
mini9 pong
trident1 pong
trident2 pong
trident3 pong
trident4 pong
trident5 pong
trident6 pong
````

Related:

* https://docs.ansible.com/ansible/latest/plugins/callback.html#setting-a-callback-plugin-for-ad-hoc-commands
