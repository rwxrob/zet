# Prefer Site Kubernetes Dev Cluster

I've learned a hard lesson on this new cloud-native job. I lost a full
month getting my local `kind` cluster working and setting up my
registry and everything. I learned a fuck-ton doing it. But I could have
just used the `dev` cluster at work instead --- especially now that I
know I did *not* have to use their provided "login" server and can just
use my own Docker container on my laptop to connect directly to the
Kubernetes cluster after having done our `kubectl-login` script, which
is mostly just a convenience.

One of the *major* reasons to use the provided `dev` cluster is because
of all the customization that takes place in any Kubernetes environment.
In my immediate case, they have decided to use Istio instead of Ingres
(because they used it before Ingres was even a thing). This means that
anything I would have explored and experimented with with Ingress would
have simply been wasted learning, only applicable someday, somewhere, at
another site. Had I learned on `dev` (as I'm doing now) all my knowledge
would be immediate relevant to this situation (albeit creating biases in
my learning not unlike just learning OpenShift would do).
