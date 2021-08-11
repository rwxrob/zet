# Never Put ElasticSearch on Network Attached Storage

GPFS goes down and all ElasticSearch indexes using it are instantly
corrupted, irrecoverably. "But why are you putting ES on NAS?" No good
reason exists. Now the indexes have to be recreated, which is not a
quick process. 

This isn't because ElasticSearch is shit software written in Java (as
you might initially conclude). It's because ES might be able to run for
a short time over network attached storage, but the Apache Lucerne
search engine which uses a pseudo-filesystem of its own, is extremely
sensitive to any lost data. 

ES depends very much on highly available local storage with 100%
reliability. That’s nothing surprising, every single database and search
engine on the planet depends on these things. Using network attached
storage — even as a stop-gap for such things — is a laughable
architectural decision. Just imagine the proposal.

"Let's put our critical Kubernetes logging, tracing, and observability
solution — which all the product documentation and our customer
account reps have told us requires high-performance local block storage
— on network attached storage that uses GPFS (which has customizations
from IBM just for our company). For now we'll just let our users
'practice' using it. They'll understand not to depend on it, for now.
Later, after procurement has approved our hardware request, we will
migrate once we have the *right* hardware. That should be fine."

*Silence, then ...*

PFFFFHAHAHAHAHHHHAAAAAHAHAHHAHAHHAHAHAAAHAHA!

