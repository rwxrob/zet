# Helm Deployment from Hell, A Reality Check

By now you've probably heard of Helm and used it to deploy software into
your Kubernetes cluster. In fact, in 2022 it is now required learning
for the certification exam. But let's be honest, Helm is horrible.
You've likely learned this yourself. Helm is not what you were sold when
you first heard about it. 

**Helm is not a "package manager"** like `apt` or `yum` or whatever. In
fact, the only thing Helm has in common with a *true* package manager is
the aggregation of lots of stuff that eventually needs to be installed
and a few common top-level usage verbs: `deploy`, `uninstall`, etc.

**Helm charts are not packages.** Charts are just a bunch of YAML and Go
templates organized in no particular way. There's no standard, no
convention, nothing. Every single chart does things slightly differently,
which would be fine except ...

**Helm requires you to read chart files to be sure you get what you
want.** You simply cannot trust a Helm chart all by itself. If you
haven't learned this lesson by now, you definitely will. I'm a noob, but
I now consider it a fundamental best practice to read almost every
fucking line of the Helm templates and values to actually understand
what the chart is going to do (or not do) to my cluster. Not doing so is
simply foolish. 

**Helm charts are *not* easy to create and frequently contain
problems.** Kubernetes is crazy complicated meaning that those creating
Helm charts inevitably fuck it up simply from the nature of the task
complexity. At a minimum, you must add OPA Gatekeeper policy constraints
that apply to your cluster and are therefore almost never hard-coded
into any chart meaning you either use their escape hatches to add them
or fork the main template and add them directly there since they were
omitted, or monkey patch your additions after Helm does its install from
a bash script.  This insanity is decidedly different than any "package
manager" I have ever used where you can safely trust most packages to do
the right things (but not always). Bottom line: you better at least read
your chart code before installing it and you'll probably have to write
more code to do what you want. You've been warned.

**Helm obfuscates an already complicated Kubernetes resource YAML
syntax.** Just when you got good at "YAML Kubernetes programming" you
realized that Helm chart creators have taken liberties with even the
most consistent stuff, like a Deployment's
`.spec.containers[].resources.limits.cpu` and have buried it under the
whimsical monikers decided by the persons who created the Helm chart.
This is infuriating. In my experience, these non-coders who created the
Helm chart either force you to alter the chart source code itself
(removing the entire value proposition of putting it into a chart in the
first place) or they add something like `extraConfigs` that you would
never guess without having read a dozen other charts that follow the
same non-convention.

"So what is a cloud-native engineer to do?"

**Avoid Helm whenever possible.** I know it is an unpopular opinion. But
I now have substantial, personal, objective evidence that creating
deployments that depend on Helm is a fucking disaster waiting to happen.
I will only do it when forced to do it. It is far simpler to simply
write a Go single binary to handle all your installs and uninstalls
following a common, intuitive convention. You can still use Go templates
and YAML files to allow people to pass in their configurations and
customizations, but make your main deployment mechanism a single Go
binary that can be easily versioned and managed as the *software* that
is it.

**Helm is a fucking disaster, but it's not all Helm's fault.** In my
opinion, Helm is one of the worst designs ever conceived. But, it is not
Helm's fault entirely. The entire "declarative" model of Kubernetes is
just fundamentally broken on several levels. Things that should have
been coded are written in complicated, obfuscated configuration files
with obscure logic that is every bit as real as what would be scripted,
but has to be captured in YAML declarations, except you cannot capture
logic in YAML declarations, which is why ...

**It's Kubernetes fault Helm sucks so much.** Kubernetes overengineered
complexity and insistence that *everything* be "declarative" has forced
imperative logic into things like Helm (Go) templates leaving Helm in
the very difficult middle-space between declarative and imperative. This
is why Helm is so fucking ugly. Helm templates with `if` and other
imperative constructs are the result. Its a good thing we have Helm
templates to stuff all our logic in, right?

Wrong.

**Helm (Go) templates are where the imperative stuff ends up.**
Unfortunately, the most powerful part of Go templates is entirely
omitted: creating your own operators with niladic functions, something
you could do if you didn't use Helm at all and just wrote your installer
in Go directly. Imagine if Helm tried to allow template expansion. We
would chart creators build wildly complicated Go templates, they would
even create their own extensions in Go that would likely require
compilation. Which leaves me wondering ...

**Why not just write the whole fucking thing as code --- in one language
--- in the first place?** If you are honest, you will admit that you
have at least one script or system that "wraps" Helm to get it to do
what you need, consistently (like check Gatekeeper policies before
deployment). 

**Wanna simplify you life?** Drop Helm entirely and write your own
installers for your applications in Go (and only Go). Go is drop-dead
simple to learn and already has Go templates (if and when you need them)
. By packaging your application as a single Go executable you drop tons
of unnecessary abstraction layers and obfuscation that are not only less
sustainable and annoying, but also inherently less secure. The Go
Kubernetes API and package are amazingly simple compared to the
cluster-fuck which is Helm (or even YAML resource files themselves).
Just write it in Go.

> 🤬
> Unfortunately, I'm not allowed to even suggest coding such things in
> Go on my current team because almost none of them know Go and, after
> all, they are "infrastructure engineers" so "why the fuck should they
> be required to learn Go?"

**"What about consistency?"** The Helm scenario from Hell I've described
is anything but consistent. You already have best possible consistency
with the Kubernetes API itself and Go package itself. The reason it is
no more work to get your users to understand your single command than it
is to use Helm is because of all the reality that Helm forces on you.
You *are* coding when you install a Helm chart. This is not some fucking
`apt install yourapp`. You have coded YAML files, and sometimes template
extensions forcing you to "fork" the original chart. You've added
scripts for things that cannot be done in either YAML or templates, like
applying OPA Gatekeeper policy checks (which Helm does not do). (I know,
I keep repeating that. It's still fresh.)

**Helm claims to simplify installation but doesn't.** For all the
reasons mentioned you end up with a complicated, per-chart cluster-fuck
you have to pick apart, extend, and paste back together with home-grown
bash scripts to get a consistent deployment working at all. Why not just
use *actual* resource files and Go templates as a best-practice and drop
Helm entirely? Just code it in Go, if you are allowed.

    #rant #helm #cloud #k8s #golang
