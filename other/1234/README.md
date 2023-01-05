# Peiter Lange's kube-backup Script

I can only assume Peiter works for RedHat these days given that his
kube-backup script is in Quay.io and not a part of several enterprise
backup solutions, which I find amazing given its terse description from
the README.md:

> Quick 'n dirty kubernetes state backup script, designed to be ran as
> kubernetes Job. Think of it like RANCID for kubernetes. [Lack of
> capitalization is his.]

This was last updated on January 13, 2020. That's soon to be three years
ago. Maybe that means it is stable. Maybe not. I'm looking into it.

The idea of it is simple enough. Just copy down *every* Kubernetes
resource as YAML and store it regularly into a Git repo.

I'll have to have a closer look when setting up my own on-prem hardware
cluster, still I have to look for better backup solutions out there. I'm
still blown away that anything "quick 'n dirty" is the basis for most
enterprise production cluster backups, 'cuz it apparently is.

> 🤬
> By the way, did I mention that the name "kube-backup" is a violation
> of the official reserved naming conventions posted on Kubernetes
> official site? There I just did. This hack has nothing to do with
> anything official and therefore should never have used the "kube-"
> prefix, but, oh well. The definition of "quick 'n dirty" apparently
> includes thumbing your nose at official naming reservations and other
> silly rules. I'm not impressed. For someone to not know that and yet
> still have this be the basis for production cluster backups scares the
> shit out out of me. 

Something else that I'm really having a huge time swallowing is the
publication of *every fucking secret in the production cluster* into a
flat, unencrypted GitHub repo protected with nothing but GitHub's access
restrictions. All it takes is one dumb-ass with access to that repo to
get phished, brute-forced, or to pull down a copy of that repo onto a
shared drive (or any insecure computer) for a would-be hacker to own the
entire fucking production cluster. No wonder Kubernetes headlined at the
2021 DefCon. There has to be a better way. There just has to be.

This entire thing has really been a revelation of just how fucking
stupid the baseline practices and design patterns are for Kubernetes
security in general. Before hackers got access to one or more servers,
now they get *everything*. It's a great time to be a hacker, that's for
sure.

Related: 

* [20211026164332](/20211026164332/) Do Not Create Namespaces Beginning with `kube-`

Tags:

    #k8s #tools #backups
