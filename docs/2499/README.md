# Go yaml.v3 fails to parse global tags like !!str

Be warned, the following valid YAML string (scalar) document is not parsed correctly by Go `yaml.v3` or `yaml.v2`.

```yaml
%YAML 1.1
--- !!str
title: YAML Ain't Markup Language™
---
another: thing
---
some: random thing
```

The following works, however:

```yaml
%YAML 1.1
--- |
title: YAML Ain't Markup Language™
---
another: thing
---
some: random thing
```

As does this:


```yaml
%YAML 1.1
--- >
title: YAML Ain't Markup Language™
---
another: thing
---
some: random thing
```

