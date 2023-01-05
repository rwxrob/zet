# Use `yaml:",inline"` as Catch All

*UPDATE: yaml.v2 is bork and does not work with this. You will get an
error every time you try to marshal your structs as JSON. Use v3 instead
(like the Kind project does).*

People seeing the `inline` tag parameter for unmarshaling structures in
Go might be confused. It is a catch all from  gopkg.in/yaml.v3 package
that reads everything from that point on into the map or struct. It is
*extremely* valuable when dealing with files that might contain fields
that you do not want to upset or overwrite. It allows any YAML file to
be parsed without fear. In fact, it is so powerful it is really a reason
to choose YAML for your configurations over JSON all by itself. There is
currently nothing equivalent to it in the JSON Go world.

>  Inline the field, which must be a struct or a map, causing all of its
>  fields or keys to be processed as if they were part of the outer
>  struct. For maps, keys must not conflict with the yaml keys of other
>  struct fields.

I first learned of this trick by inspecting the code of the amazing,
award-winning Kubernetes utility, Kind. Kind uses it to modify the
`~/.kube/config` file without fear of destroying the users existing
YAML contexts and other configurations.

Note that this does *not* work with `github.com/ghodss/yaml` (which has
other advantages). You must always use the `yaml` tag and not the `json`
one. But this is usually not a problem. In fact, since JSON *is* YAML
you can just use the YAML library for everything and forget about all
the JSON encoding stuff completely.

Here's a sample from the "lab":

```go
package main

import (
	"fmt"
	"log"
	"os"

	"gopkg.in/yaml.v3"
)

// this works
type Foo struct {
	One int            `yaml:"two"`
	Two int            `yaml:"one"`
	O   map[string]any `yaml:",inline"`
}

func main() {
	foo := new(Foo)
	buf, _ := os.ReadFile("foo.json")
	if err := yaml.Unmarshal(buf, foo); err != nil {
		log.Print(err)
	}
	fmt.Println(foo)
}
```

Produces

```out
&{2 1 map[other:[1 2 3] some:true]}
```

And yes this works fully with YAML reference (`*`) and anchors (`&`).

* yaml package - gopkg.in/yaml.v3 - pkg.go.dev  
  <https://pkg.go.dev/gopkg.in/yaml.v3#Marshal>

* <https://github.com/kubernetes-sigs/kind/tree/main/pkg/cluster/internal/kubeconfig/internal/kubeconfig>

    #golang #json #yaml #marshaling
