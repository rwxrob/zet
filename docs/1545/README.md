# SRE and Infrastructure Engineering About Upgrading

I'm reminded that pretty much every operations career is generally just
a huge loop:

1. Install stuff and assert you did it right
1. Look for problems with that stuff, fix, and report
1. Wait and prepare for new releases of that stuff
1. Repeat

There *is* a lot of development (hence the whole "SRE" admins-who-code
thing) but it is often one-off, auditing, and report generation (which
demands exceptional shell scripting skills). In that regard, there is
some similarity to the security related careers, except the reports
don't have to as polished because they are for internal use and not
handed over to paying customers.

Often you have to double as the guru that helps people use the stuff you
installed. Usually, you are installing stuff that is not being requested
by people who need it, but people who *think* everyone needs it (usually
with very pointy hair). This means you are filling an education/support
role as well.

I have to grin because no matter how much the technology improves I
inevitably sit on calls planning (and recovering) from this stuff. In
fact, in the cloud-native space the CNF actually had to slow down the
new version releases of Kubernetes specifically because the entire
industry cannot keep up with their release cycles and upgrades (not to
mention cannot find qualified people who understand the full complexity
of it all). 

More importantly, the scale of these updates is huge. This isn't like
updating a few servers or database instances or web servers at a time
(like before). This is upgrading the *entire* infrastructure for
everything within a cloud-native enterprise in one shot. While that
may decrease upgrade times, it dramatically increases the risk
--- particularly if not done right and because it is virtually
impossible to roll this stuff back once you upgrade it. Now add the
level of complexity involved in a typical cloud-native deployment, so
many moving parts, so many different vendors, so few people who
understand all of it. This comes at additional cost in terms of risk.
Risk managers have got to be freaking out over the new normal. I do.

I find it absolutely mind-boggling that people throw traditional
change-management cycles out the window for "CI/CD" in the face of this
risk. You haven't removed any risk at all, you've just moved it around
and, frankly, often smothered it in complexity that adds more risk.
