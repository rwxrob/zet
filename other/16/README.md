# Use YAML References and Anchors

One of the least appreciated used of YAML that set it far and away
better than JSON for configuration sorts of things. I use this to make
aliases in my Twitch bot commands.yaml file.

```yaml
some_thing: &VAR_NAME foobar
other_thing: *VAR_NAME
```

And yes, this works with gopkg.in/yaml.v2 `inline` which I use in my
yaml2json Bonzai command.

* <https://github.com/rwxrob/rwxrob/blob/main/twitch/commands.yaml>

* <https://github.com/rwxrob/yaml2json>

* YAML Cheat Sheet & Quick Reference  
  <https://quickref.me/yaml>

    #yaml #tips #json #configuation
