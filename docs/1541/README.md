# Kind for Fast, Minikube + KVM2 Driver for Real

"Should I use Minikube or Kind to learn Kubernetes?" 

Yes. Both are amazing and essential. Kind is the lightest weight and the
fastest to setup, but Minikube --- with a true virtual machine driver
like KVM2 --- is the fastest *real* setup.

I discovered this while trying to blow up a storage class to see what
would break and how I would know (so that I could write software to
prevent that from happening). Such a task is very precarious with Kind
since there nothing protecting you hard drive that is being used as the
default StorageClass. But with a VM (in Minikube) there is no danger
even if I fill the disk. This is perfect for *really* testing scenarios
you hope you never have to see in the real world. It's like being about
to do controlled burns as a firefighter and get good dealing with them.
Minikube is *ideal* for this.

It's worth mentioning that if you want to get hands-on experience
installing an enterprise scale simulation of Kubernetes on machines
using `kubeadm` that Vagrant with the libvirt driver allows for that. It
sets up all the emulated virtual machines your workstation can support
(about 1 per 1 Ghz of CPU) and then you are free to do the rest.

Tags:

    #cloudnative #k8s #testing #operations
