# Your `json:",inline,omitempty"` is Really YAML

People seeing the `inline` tag parameter for unmarshaling structures in
Go will be really confused because the `encoding/json` package does not
support it, the gopkg.in/yaml.v2 package does, and people using
ghodss/yaml are free to use `json` instead of the `yaml` tag. So 
it is yaml.v2 that is handling the `inline` tag, not anything to do with
JSON.

"Why do I care?"

Because sometimes you don't need all the fields, but also don't want to
lose them when writing them all back out again, like Kind does when
messing with ~/.kube/config file:

>  Inline the field, which must be a struct or a map, causing all of its
>  fields or keys to be processed as if they were part of the outer
>  struct. For maps, keys must not conflict with the yaml keys of other
>  struct fields.

That means you can throw everything in there and only focus on the stuff
you want/need without fear of creating something that might be too
brittle and break later because your copy of the struct does not
coincide with that of the API (which is *exactly* why Kind uses it)..

* yaml package - gopkg.in/yaml.v2 - pkg.go.dev  
  <https://pkg.go.dev/gopkg.in/yaml.v2#Marshal>

* <https://github.com/kubernetes-sigs/kind/tree/main/pkg/cluster/internal/kubeconfig/internal/kubeconfig>

    #golang #json #yaml #marshaling
