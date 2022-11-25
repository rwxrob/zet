# Keep outlines in markdown, not YAML

It might feel like a good idea to maintain an outline in YAML so that it can be reliably parsed and have fields added to it and such, but the practical reality is that just maintaining one in Markdown is always easier. Here are a couple of examples:

```markdown
# Outline

1. one here
   1. a sub under first
1. two here.

```

Both of the following don't do what you want:

```yaml
Outline:
- one here
  - a sub under first
- two here
```

Which produces the following:

```yaml
Outline:
  - one here - a sub under first
  - two here
```

Or the following which accomplishes about the same thing, but in a very confusing way. This creates a dictionary/map just so that it can have subheadings.

```yaml
Outline:
- T: one here
  C:
    - a sub under first
- T: two here
```
