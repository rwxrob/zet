# Declarative Fails Again: K8S NFD Adds YAML Operators

It's happening again. I'm sure the decision to not use Helm was because
Helm charts are too heavy and unmanageable. So the Node Feature
Discovery project decided to use `kustomize`. I can't fault them for
that. But somewhere along the path they added 10 "operators":

```yaml
op:
  description: Op is the operator to be applied.
  enum:
  - In
  - NotIn
  - InRegexp
  - Exists
  - DoesNotExist
  - Gt
  - Lt
  - GtLt
  - IsTrue
  - IsFalse
```

By the way, I removed more than 30 spaces of indentation on that shit. I can't wait until `yaml.v3` forces arrays to be indented by four spaces. This YAML would be utterly unreadable on a screen that even allowed 200 columns.

Then, you see this all over:

```yaml
matchFeatures:
  - feature: cpu.cpuid
    matchExpressions:
      AVX512F: {op: Exists}
  - feature: cpu.cstate
    matchExpressions:
      enabled: {op: IsTrue}
  - feature: cpu.pstate
    matchExpressions:
      no_turbo: {op: IsFalse}
      scaling_governor: {op: In, value: ["performance"]}
  - feature: cpu.rdt
    matchExpressions:
      RDTL3CA: {op: Exists}
  - feature: cpu.sst
    matchExpressions:
      bf.enabled: {op: IsTrue}
```

> 💢  
> I think I done working in Kubernetes. I'll get my certs and get the fuck
> out. I can't take this shit. This stuff is just so fucking ugly and apparently
> people don't see any problem with it. Helm is starting to look better.

I've been down this path myself with `scan.X` where instead of just
writing code, I created a bunch of structs that added as operators in a
full-blown, in-Go interpreted language. That's a very bad idea. Just
write (or generate) Go, or whatever. NFD is headed down this dark path
as well.

This particular decision isn't particularly egregious, it's what comes after
this that concerns me. Should we encourage every possible
Kubernetes application to invent its own YAML-based language? 

The OPA Gatekeeper challenger Kyverno has done the same thing, but way worse:

```yaml
    validate:
      message: "The usage of hostPort is forbidden"
      anyPattern:
      - spec:
        containers:
        - =(ports):
            - X(hostPort)
      - spec:
        =(initContainers):
        - =(ports):
            - X(hostPort)
```

To be fair, OPA uses Rego, and entire fucking language just for this shit. YAML isn't that answer, but is Rego?

The root cause of the problem is forcing all of this to be declarative. The
declarative model continues to fail Kubernetes in general. Sure it is fine for
declaring the state of machines and RAM and such, but it fails miserably to
"declare" what an application looks like that runs in such an environment. 

Just look at all the different ways people have tried to do this, Helm (which
is *not* a fucking "package manager", stop fucking calling it a "package
manager"), operators that have root to everything on the planet, and now
home-grown languages that live in YAML from `kustomize` and others. All of this
shit is *because* of people forcing declarative on everything. Someone needs to
have the courage to just make a way to create apps that is *not* declarative,
that is like a *true* package manager where shit actually runs during
installation and when uninstalling.

* [20210715174454](/20210715174454/) Always Read the Helm Chart Templates
* [20210913155012](/20210913155012/) Helm Deployment from Hell, A Reality Check
* [20211116115952](/20211116115952/) Helm All the Things
* [20211118155755](/20211118155755/) K8SAPP Helm Procedure
* [20211130172230](/20211130172230/) K8SAPP Gotchas: Helm Does Not Create Namespace
* [20211116021352](/20211116021352/) Kustomize

    #k8s #nfd #rants #yaml #cloudnative
