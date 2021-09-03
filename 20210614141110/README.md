# Istio VirtualService `host` Actually Means Service

Terms matter --- especially to me. It drives me crazy that Istio decided
to name the `spec.http.match.route.destination.host` instead of
`service` since that is the value required.

However, it turns out that are is an explanation for this. Istio can be
run on VMs without any need for it to be in Kubernetes at all (even
though the YAML file and `kind: VirtualService` is enough to throw
anyone off to that fact.) I concluded Istio was only a Kubernetes thing.
But I'm told that is not true. So that solves the mystery of the
horrible naming. Maybe someone else will find this helpful and avoid the
confusion I wasted an hour trying to figure out.
