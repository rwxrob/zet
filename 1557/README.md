# Deleting Kubernetes Namespace Deletes Everything

Don't know what I didn't discover this before, I knew that Kubernetes
namespaces were logically being used to encapsulate all the different
components of a specific system, but I did not realize that deleting a
namespace cascades the delete to everything in it. This is huge (and
dangerous). It means that anything you put into Kubernetes should really
*always* have a namespace associated with it so you can add and remove
stuff in your thing just by using the namespace.

Although I haven't done this yet, I could easily see leaving off the
namespace when just constructing multi-object applications. This is why
Helm, in spite of its quirks, is a thing that people use.
