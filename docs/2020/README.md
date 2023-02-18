# Use Hashicorp go-plugin for clean abstraction

The `go-plugin` project has been around *forever* but few really know about it. It is the best way to separate coding projects without creating performance bottlenecks. One advantage is that the licensing --- and even the implementation language --- or one plugin doesn't have to agree with the main system using the plugins. This separation of project management as well as implementation makes it a no-brainer, best-pick for such things. This is why all the major Hashicorp applications use it (and have since 2018).  There really is no other plugin system that is more mature at this point, certainly not Go's own (broken) shared library plugins (which are horrible because they cannot be unloaded and take down the entire process if something goes wrong).

* <https://github.com/hashicorp/go-plugin>
