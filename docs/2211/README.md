# Extending Golang templates with FuncMap

Careful to be sure to include the exact name of one of the files parsed otherwise the `t.Execute` won't find the template.

```golang
  custom := template.FuncMap{
    `foo`: func() string { return `bar` },
  }

  data := map[string]any{`this`: `that`}

  t, err := template.New(`tutorial.txt`).Funcs(custom).ParseGlob(`files/*.txt`)
  if err != nil {
    log.Fatal(err)
  }

  if err := t.Execute(tutfile, data); err != nil {
    log.Fatal(err)
  }
```
