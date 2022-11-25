# Helm 2 to 3 Migration Considerations

It is extremely unfortunate that the Helm team has provided virtually
zero direction about how to go through the migration from 2 to 3. (I'm
less impressed with Helm as a team and company every day. The evidence
keeps piling up.) 

Something as basic as detecting which version is installed you would
think would have been the fucking first thing they documented. (Perhaps
they did, but after an hour I could find nothing.) So here's the best
researched solution I could come up with in a few hours.

First we have to get all the user namespaces:

```bash
names() {
  IFS=
  while read -r line; do
    name="${line%% *}"
    test "$name" = NAME && continue
    echo "$name"
  done < <(kubectl get ns -l "nstype=user")
}
```

Then we have to determine if Tiller (a Helm 2 only thing) is in that
namespace specifically:

```bash
tiller_exists() {
  kubectl get deploy -n "$1" | grep tiller-deploy &>/dev/null
}
```

That will produce a 0 if `tiller-deploy` is included in the deployments,
which is true for every new user under Helm 2 (as far as I can tell).

We still need to check if Tiller is actively running in that namespace
at the moment in order to run the upgrade script, otherwise it will just
fail. It can be installed and just not running:

```bash
tiller_is_running() {
  helm2 list "--tiller-namespace=$1" &>/dev/null
}
```

Normally this produces something like the following if *not* running:

```
Error: could not find tiller
```

Again, Tiller *is* there, just not running at the moment, which is why
the first `tiller_exists` is needed.
