# REST is Alive and Well, Despite GraphQL

The world might be gaga over GraphQL, but it is still running on REST.
In fact, Kubernetes is *mostly* a monstrous REST API and as I was
recently reminded, a k8s "Service" is a "REST" object:

> A Service in Kubernetes is a REST object, similar to a Pod. Like all
> of the REST objects, you can POST a Service definition to the API
> server to create a new instance. The name of a Service object must be
> a valid DNS label name.

Given the substantial momentum of all things cloud-native it is safe to
say that mastering the methods and means to creating, managing, and
consuming REST APIs is a solidly career requirement for most people
working in tech for the foreseeable future. In fact, it wasn't until I
started looking at the Kubernetes REST API to find an associated method
to match it that I discovered [Swagger], which had me feeling like I was
late to the party, again. Swagger has good and bad stuff like most tech,
but it makes short work of code generation for otherwise extremely
complicated REST APIs, both for the clients and the micro-services
providing them.

Bottom line: learn REST and all the tools that go with it, yes including Swagger, `curl`, `httpie`, PostMan, and yes, learn GraphQL as well.

[Swagger]: <https://swagger.io>
