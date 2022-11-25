# Use Skopeo for Moving Container Images Around

```
skopeo login <registery>
skopeo copy --override-os linux docker://<from> docker://to
```

Yeah, you don't need Docker (thank god). This is particularly useful for
Mac users (forced to use Mac because of corporate requirements, but who
don't have docker running on their laptops). Don't forget the override
because lots of container images don't have a `darwin` version
(`gpu-feature-discovery` from Nvidia, for example).

Recently, I was told about Skopeo, a useful tool for moving images
between registries --- particularly when moving from the Internet into a
private enterprise repository in Harbor or Portus of something. It's yet
another tool that isn't included in the list when people start getting
into Kubernetes, and more proof that just learning Kubernetes is never
enough. In fact, it's all the different tools that fulfill Kubernetes
and supplement it that are the real things anyone needs to learn.

* Work with remote images registries  
  https://github.com/containers/skopeo

* "no image found in manifest" error explanation  
  https://github.com/containers/skopeo/issues/634

    #k8s #cloudnative #containers
