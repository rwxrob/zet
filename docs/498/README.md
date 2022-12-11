# Serverless is dead (case you didn't hear)

> The fact is, serverless technology is amazingly simple to start, but becomes a bear as projects and teams accelerate. ... Combining all of these into a serverless project become a huge nightmare for the following reasons. (Brent Mitchell)

The last time people got excited about "serverless" (including me) was in 2020, and even then some predicted its downfall. After all, Kubernetes was dominating then and continues to fully dominate now. If people need something lighter than Kubernetes they reach for Nomad. I was surprised there weren't more search hits talking about this. KNative, a "serverless" option that requires Kubernetes to run demonstrates how ironic the whole questions of serverless has become.

I'll admit I was a huge fan of *the idea* of Amazon Lambda as a developer. I'm not any more. It covers all the right things that a lonely developer wants to hear.

"What?! I don't need a whole platform (or Heroku)? I can just write "functions" in my favorite language?"

It's extremely appealing. It's also complete fantasy fiction. Anyone who has managed infrastructure or applications will tell you that there is still a lot of work to be done, that the integrations with systems will immediately make such things impossible, that vendor lock-in is beyond acceptable when depending on Amazon for the very code execution and not just the infrastructure.

It's no surprise astute software architects are seeing it for that it is, a huge ploy from Amazon to force permanent, dependency on their proprietary system, 'cuz that's what it is. They can fool you into thinking you can write in any FOSS language, blah, blah. But they want you to be permanently stuck there.

The reality of any significant application development is that there are so many moving parts on the backend before an application even makes it to the user that simplifying all of that into a few "functions" is just ludicrous. People (like me) might hate the complexity of Kubernetes, but the fact is, that complexity was born from delivering perhaps the most successful application of our time: Google. It doesn't matter what you think of Google. I'm talking about the architecture. Sure K8S goes overboard on many things, but in this case too much is better than not enough, and "serverless" will *always* be "not enough." Besides, it's a fucking idiotic moniker in the first place, obviously there's a server, someplace.

Most people reach for serverless for the wrong reasons. Serverless is a really bad bandage on an arterial hemorrhage:

> For a lot of these organizations, it's hard to find the time, people, and money to figure out how to automatically provision new VM's, get access to a K8S cluster, etc. My challenge to you is to first fix your deployment and scaling problems internally before thinking about serverless compute. (Brent)

In fact, we are starting to see movement toward Kubernetes approaches on the Internet itself, a cluster of clusters, microservices exchanging Protobuf (instead of JSON) at gRPC speed to one another over the open Internet. Kubernetes is on its way to breaking out of the enterprise walled gardens of the world, "hybrid" is the new hotness, where cloud providers can seamlessly communicate with on-prem services to provide one Kubernetes cluster to rule them all. The adoption of WASM in the browser just furthers that future, a much better future, for everyone, built on open standards and faster than anything Amazon Lambda, KNative (or any of the clones) will ever be able to  provide.

A few major things need to happen before the *Kubernetes Internet* (a term I think I just invented) becomes a reality, support for gRPC native in the browser, for one. It definitely will happen.

Why should you care?

There's not enough time to learn everything. But be sure learning "serverless" anything isn't going to end up wasting your time later. Learn Protobuf, gRPC, containers, and Kubernetes. And --- for the love of God --- ***learn Go***. It's everywhere! Everyone agrees Go is "the language of cloud" and when cloud becomes Internet Go that means Go becomes "the language of the Internet." Learn these today. Protobuf and gRPC applications will overtake every other application on the planet. Front ends will get significantly smaller as more of the processing returns to where it
belongs --- on the server.

* Why the Serverless Revolution Has Stalled  
  https://www.infoq.com/articles/serverless-stalled/

* Is Serverless The End Of Kubernetes?   
  https://towardsdatascience.com/kubernetes-serverless-differences-84699f370609?gi=1e4f35571fc3

* https://dev.to/brentmitchell/after-5-years-im-out-of-the-serverless-compute-cult-3f6d

* https://qemu.readthedocs.io/en/latest/system/i386/microvm.html
