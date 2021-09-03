# Implied KEG Node Types

Rather than create a complicated system and syntax for declaring types
within a global domain scope (as XML and YAML and many others have
done), KEG node types are simply implied by the fields used. For
example, an `Outline` type simply has an `Outline:` field. This allows
content creator to quickly create types without over thinking it. When
and if typing conflicts arise between different KEG sites a root `TYPES`
node can be provided that provides the JSON-Schema-as-YAML
specification.

This approach also allows any KEG Node to fulfill multiple type
definitions when it is practical to do so. For example, a KEG node
`Base` type is required to have nothing more than a `Name:` field. So an
`Outline` type fulfills the type specification for *both* `Outline` and
`Base`.
