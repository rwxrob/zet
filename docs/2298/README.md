# Why change management matters, yes even now

Last week we went through five days of having a half-dozen people dedicating all their time to finding out what broke the Thursday before. Then the guy on vacation returned and find the problem in a few minutes.

"Oh yeah, this happens all the time. It's a `kill_errant_containers` cronjob that kills the production Kubernetes pods when it is put on the wrong machines."

I'm sorry. I'm just not good enough to look into cronjobs explicitly killing Kubernetes pods on production servers. Call me naive, but I just don't assume shit like that ever makes it into production. Why? Because I was raised on "change management" at IBM (and the ISPs before). Nothing changes on production systems without peer review and sometimes an change ticket and outage window.

Since I have been at this particular company *no one* follows any sort of change management whatsoever. In fact, the guy who interviewed me (who left the company for better opportunities last year along with all the rest of the original team) actually bragged about never once filling out a change management ticket during the 10 years of employment with this company. I thought my surprise was out of place, that perhaps I was now a fossil and CI/CD and other dynamic monitoring removed the need for good ol' change management.

Then last week happened.

The thing that annoys me the most is that everyone is saying things like, "We can never let so-and-so go on vacation" in jest like this is some funny shit. It's not. Thousands of dollars were lost, maybe 10s of thousands in lost jobs in the cluster.

The fact that having one person not go on vacation would have prevented this outage is a huge black mark on our team. Either that recurring issue should have been documented and communicated clearly to the whole team so we could watch out for it, or it should never have happened in the first place because even rudimentary change management controls were in place. Either way, it was a *massive* fail for our operations team.

I hold no ill will toward this person. I just want to write about this situation to help others realize that production change management is not some archaic practice that only old farts like me suggest. Change management may have morphed in a world of CI/CD, but it has not gone away. At a minimum every single change that hits any production system, through GitOps or whatever, should be carefully scrutinized, every change window should be well documented to ensure what happened and when, and changes and recurring issues should never go undocumented. Had we had a change management system into which this recurring issue had been reported we could have looked for it. Had the changes that were made on that day actually been documented we could have looked for it. Instead, our production Kubernetes cluster took a major hit because someone was working in prod without a net and without any peer review.

Don't be us. Be better.
