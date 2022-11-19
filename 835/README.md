# VM in Container, or Container in VM?

Do you remember that 'chocolate in my peanut butter, peanut butter in my
chocolate' advertisement? Well that's the difference between `kind` and
`minikube`. In a very simplified way, Minikube is a virtual machine with
a container engine inside of it, while Kind is a container engine with
'machine' images inside of it.

Which should you use?

Both are amazing tools, but the Kubernetes project and CNCF have
officially backed Minikube as best for learning and working locally with
Kubernetes on your own workstation.

Kind was and is used by test Kubernetes itself. It's an amazing, simple
tool, but it lacks many things that are required to get a true sense of
working with a Kubernetes cluster.

For all intents and purposes, Minikube is a fully separate network of
computers encapsulating a Kubernetes installation in *exactly* the same
way you would encounter if working with one in the enterprise or on your
own home multi-node lab. What feels like an inconvenience, mounting
directories into it, for example, is actually *exactly* what you want
for a beginner experience. It is the same.

Minikube is also *designed* for beginners and installs easily on Mac,
Windows (WSL2 isn't even required) or Linux. No need to install Docker
or anything else. Just a single thing and you get `docker`, `kubectl`
and everything else for free (which is literal as well since Docker
Desktop costs money if you are doing it for work).

> 💬
> I really did not get the value of Minikube when I started because many
> people told me to use Kind. I now regret that decision and wish I had
> learned on Minikube instead for reasons I talk about in many places in
> my notes.

    #k8s #minikube #kind #docker #cncf #cloud #tips #tools
