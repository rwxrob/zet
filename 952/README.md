# Keep Outlines in Markdown, Not YAML, Use PEGN

It might feel like a good idea to maintain an outline in YAML so that it can be reliably parsed and have fields added to it and such, but the practical reality is that just maintaining one in Markdown is always easier. Here are a couple of examples:

```markdown
## Outline

1. one here
   1. a sub under first
1. two here.

```

And the minimal possible YAML equivalent:

```yaml
Outline:
- T: one here
  C:
  - T: a sub under first
- T: two here
```

Looks like it is time to get PEGN going again. Imma be parsing directly from Markdown a lot more and needs a much better AST.
