# Minikube KVM-QEMU driver seems most stable

I've had such solid performance and no-quirks stability with the KVM-QEMU backed minikube running on Linux (VM or metal) that I won't use anything else. It is so good it feels like I'm running my own vanilla kubernetes cluster that I built myself. I even question if I *ever* want to run my own cluster when I can run an amazing turn-key cluster anytime with minikube using this driver.

Moreover, this was confirmed by one of the most experienced members of my livestreaming community as well. At first I was concerned that the VM nature of the host linux OS for minikube would present a kvm-inside-kvm problem, but so far it appears not.

*This zet once had a bunch of stuff about why VirtualBox was the best. I was so wrong.*
