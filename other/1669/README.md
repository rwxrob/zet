# Use `yqlib` to Add YAML Selection

Let's say you want the power of `jq` and `yq` like selection syntax for
your YAML files. Turns out that the creators of `yq` have gracefully
exposed `yqlib` so that we can use it directly. I may not agree with
several of their design decisions, but it doesn't matter. This works (at
least until I can get PEGN and scan.X fully working so this stuff
becomes trivial once you have a proper spec written in PEGN).

Here's a `sample.yaml` file:

```yaml
foo: FOO
bar: BAR
other:
  - one
  - two
  - three
```

And here's the code from my <https://github.com/rwxrob/lab> where I
figured it out. It's anything but pretty, but it fucking works:

```go
package main

import (
	"io"
	"log"
	"os"

	"github.com/mikefarah/yq/v4/pkg/yqlib"
	logging "gopkg.in/op/go-logging.v1"
)

// creating a printer is a pain in the ass, but flexible

func NewYamlPrinter(
	w io.Writer,
	f yqlib.PrinterOutputFormat, // i mean, what the fuck
	unwrap bool,
	colors bool,
	indent int,
	sep bool,
) yqlib.Printer {
	enc := yqlib.NewYamlEncoder(indent, colors, sep, unwrap)
	pwr := yqlib.NewSinglePrinterWriter(w)
	return yqlib.NewPrinter(enc, pwr)
}

func main() {

	// shitty log shit, god i HATE op/go-logging (circa 2012)
	format := logging.MustStringFormatter(
		`%{color}%{time:15:04:05} %{shortfunc} [%{level:.4s}]%{color:reset} %{message}`,
	)
	b1 := logging.NewLogBackend(os.Stderr, "", 0)
	b2 := logging.AddModuleLevel(logging.NewBackendFormatter(b1, format))
	b2.SetLevel(logging.ERROR, "")
	logging.SetBackend(b2)

	ev := yqlib.NewAllAtOnceEvaluator()
	pr := NewYamlPrinter(os.Stdout, yqlib.YamlOutputFormat, true, false, 2, true)
	dc := yqlib.NewYamlDecoder()
	//err := ev.EvaluateFiles(os.Args[1], []string{"sample.yaml"}, pr, true, dc)
	err := ev.EvaluateFiles(os.Args[1], []string{"-"}, pr, true, dc)
	if err != nil {
		log.Print(err)
	}
}
```

Note that using "-" gives you UNIX filter input from standard input.

    #golang #coding #tips #yaml #yq #yqlib
