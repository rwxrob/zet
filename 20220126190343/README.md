# Rancher Desktop Alternative to Docker Desktop

> porschephilth: no, we just bought \$50k of docker licensing while we
> get the RD rollout/process figured out. we had to take care of "right
> now" while we get the log-term process in place

> Update: 20220204 Rancher Desktop is *really* buggy and not ready at
> all for production use. Plus it makes permanent changes to your RC
> files as if you didn't care. I do. We all do. I'm really sad to see so
> many bad design decisions in something I was really hoping to love.

***WARNING: Rancher Desktop does not work with Cisco Anyconnect VPN.
Docker Desktop does (see Related). Rancher Desktop also requires WSL2
and will install it if not found. This can break VirtualBox
installations in subtle and annoying ways, like slowing all of your
VMs.***

Rancher Desktop 1.0 was just announced just in time to help large
companies deal with the looming deadline to start paying for their
corporate subscriptions to Docker Desktop (Enterprise). This is huge.
All the alternatives so far have not fulfilling the same expectation for
a drop-dead simple user-friendly interfaces to Docker. Looks like this
one does with the added bonus of providing a local Kubernetes cluster
out of the box (instead of tacking it on like Docker Desktop tried, and
failed, to do). This is huge news for those making enterprise decisions
about container tooling for their developers.

It also turns out that Rancher Desktop supports M1 Macs (while
VirtualBox still does not).

Related:

* <https://github.com/rancher-sandbox/rancher-desktop/issues/1115#issuecomment-1022901127>

* <https://github.com/rancher-sandbox/rancher-desktop>

* Rancher Desktop GA Go Live - YouTube  
  <https://www.youtube.com/watch?v=Iyj-9mgk34E&feature=youtu.be>

* The Grace Period for the Docker Subscription Service Agreement Ends Soon - Here\'s What You Need to Know - Docker Blog  
  <https://www.docker.com/blog/the-grace-period-for-the-docker-subscription-service-agreement-ends-soon-heres-what-you-need-to-know/>

* [20220125192913](/20220125192913/) Linux on VirtualBox, Best First Linux Experience

* The Time to Decide on Docker Desktop Has Arrived -- The New Stack  
  <https://thenewstack.io/the-time-to-decide-on-docker-desktop-has-arrived/>

    #k8s #docker #devops #tools #rancher #foss
