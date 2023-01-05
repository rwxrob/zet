# Use Golang `yaml.v3` with 4-Space Tabs (Not `v2`)

Been reading up on the move to `yaml.v3` in the Kubernetes code base and
other than a hiccup with comments not appearing in the right place
(fixed around Feb 2021) this looks like the solid direction going
forward.

```yaml
# this is v2
old:
- foo
- bar

# this is v3
new:
    - foo
    - bar
```

I particularly like that the lists/arrays will now be indented four
spaces by default rather than appearing inline with the parent. Once
upon a time I respected the `v2` way of lining them up to preserve that
level of indentation, but after working with Kubernetes YAML files for
the past three months (and identifying several bugs in YAML because
there is nothing catching reassignment of the same name) I have come to
*really* appreciate the change to deeper indentation. This will also
promote simpler APIs because people will run out of room. (Who am I
kidding? Most people don't give a shit about that stuff like I do.)
