# No Dashes `-` or Underscores `_` in REST APIs

There is a pretty big debate that has raged over more than a decade
about what is the *correct* method of naming a REST API endpoint. The
O'Reilly Book (that people cite as main claim to use hyphens) was
published in 2011 before Kubernetes was even out. 

I am actually really glad to see that the Kubernetes team decided on
simply dropping the case to lower for the whole thing. (The k8s API is a
thing of beauty actually, very well designed despite how massive it is.)
I plan on doing the same whenever I have the option to make that
decision.

```
GET /apis/storage.k8s.io/v1alpha1/volumeattachments
```

While I support kebab-case for URIs in general it is true that the
hyphen stops most things from selecting the entire URL. After all `_` is
considered a part of "alphanumeric" in most regular expressions
including PCRE. 

Dropping the case has the added advantage of directly correlating the
names to their mixed case actual names in ProtoBuf (gRPC).
