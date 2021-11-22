# "Package Management" Will Never Work in Kubernetes

> 🤬
> Kubernetes is not a Linux distro!

The term "package management" (popularized wrongly by the Helm project)
does not relate to Kubernetes and should be avoided. It is causing
immense confusion and chaos in the industry. Use any of the following
terms instead:

* application build utility
* configuration management assistant

Helm is closer to Webpack (a NodeJS build tool) than to APT (the Ubuntu
package manager). Calling Helm a "package manager" is simply a lie.
Let's look at an actual package manager in comparison.

When installing `openssh-server` one need only execute `apt install
openssh-server` and everything works because APT has been designed to
work with Debian/Ubuntu systems and all of those systems --- with regard
to software installation and management --- follow the same standard.
There is no intermediate validate step, no need to comb through the
source code to make sure it works on your computer, no need to add extra
dependencies that are not covered by the APT system itself, no need to
change references from external image dependencies into internal ones,
no need to copy down the package specification file to ensure we have a
copy of it. Everything just works. *That* is what a package manager
provides.

Package managers work because the distros that support them have a
contract to provide what those package managers needs. There is a
concrete agreement between the creators of the distro and the creators
of the package manager. Such a relationship *does not exist* between any
would-be Kubernetes "package manager" nor could there ever be because
every single Kubernetes cluster is completely different.

Consider the process of installing and maintaining a Helm chart. First
you identify the chart, then copy down the tarball, uncompress it, look
through the defaults with `helm template ...` read through the
templates themselves looking for bugs and places to customize, check the
Git repo to see if any of the open issues relates to you, change the
references to external images to internal mirrored copies of the images,
run the resource files through OPA `conftest` to pro-actively ensure
they meet security policies, then attempt to install only to discover
that you must create additional RBAC resources before it will even run,
and then be able to undo all of that customization once you remove or
upgrade your "package". This is *not* package management. This is
software configuration, building, and installation. Helm is *not* a
package manager. It never was. It was born out of the needs for
application creators to make it easier to *build* applications, not
install and manage them. 

Helm had good intentions, but Helm tried to provide an impossible
solution. As much as naive tech-blog writers would have you think
otherwise, Kubernetes is not anything like a Linux distribution. Every
Kubernetes cluster is unique and has its own configurations and
requirements that require a large amount of customization, even between
development and production clusters. This fact makes creating a standard
"package manager" impossible. It would be like creating an APT system
that addressed every single different Linux distro available today. The
fallacy that such applications can be managed in the same simple way is
the source of much wasted time, money, and safety.

One popular attempt at a universal solution to applications management
and installation demonstrates how ludicrous this all is. The Operator
Framework (originally from RedHat) is a disastrous security failure
requiring its OLM to have full cluster admin permissions and placing the
responsibility for cluster security on the administrators who are warned
(despite their open tickets regard this massive security flaw) to "check
anything you install with it to be sure it's safe." Imagine telling that
to APT users. Keep in mind that Helm 2 with Tiller was shamed out of
existence by the industry for attempting the same stupidity.

Ironically, even though OLM has the equivalent of (what I call)
enterprise root (root not just to one server, but your whole 
enterprise cluster) it is still unable to provide the simplicity of a
"package manager" we've come to expect when the distro is relatively
locked down. Again, the problem is with the design assumption, not the
technology. Kubernetes is not Linux distro. It's anything but. Please stop
perpetuating this dangerous comparison.

Instead, we should be focused on facilitating duplication of application
code and adding sustainable practices for maintaining that code over
time leveraging the same successful process evolved from software
applications development. Many not like to hear this, but you cannot
administer a Kubernetes cluster with software development skills,
notably GitOps, CI/CD, shell scripting, Go code review, and YAML/JSON
configuration. You simply cannot administer a collection of systems
infrastructure applications without these core skills. 

Tags:
    #rants #k8s #helm #redhat #openshift #operators
