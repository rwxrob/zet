# Kubernetes.io is Really Bork

I really love Kubernetes and the teams that support it with so much of
their own time, but the kubernetes.io site is shit. It is nearly
impossible to navigate and has glaring, obvious, basic HTML errors all
over in it. It looks terrible on a text-based browser, which people who
are particularly accustomed to lightning fast research use for stuff
like this. I have to page down 15 times to get to the content because
they made the asinine decision to include the entire outline of the site
in the whole thing every time. What's worse is the recent stuff that
appeared out of thin air confusing the hell out of me:

```
    4. Update apt package index, install kubelet, kubeadm and kubectl,
       and pin their version:
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl

cat <<EOF | sudo tee /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-\$basearch
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.c
loud.google.com/yum/doc/rpm-package-key.gpg
exclude=kubelet kubeadm kubectl
EOF
```

See all that stuff about `yum` right after the Ubuntu stuff? Yeah, it's
not supposed to be there but is because of some bork HTML template that
is getting included in the sidebar for the menu or some shit. I'm sorry,
but that is piss-poor web development right there that could easily be
fixed by using a better template and something like Hugo.

I know, I know, I can also contribute and make it better rather than
complain. But unfortunately that is not the case here. This kind of
change would require the entire site design to be redone and I doubt
anyone is thinking about that at the moment. Documentation in general
always suffers from the least amount of attention. I'd be better off
rewriting my own from scratch once I have enough skill to do it and keep
up. I just might start an initiative to do just that, like the WHATWG
did to W3.

There are a lot of people that I deeply respect who have been involved
in this effort, this is not a direct attack on them, but on the rather
shitty web site that would definitely *not* help most people during a
certification exam. And since I'm preparing for my own I'm doing to
really have to learn this stuff well without the site because the site
is virtually useless (okay, not useless, I'm just mad) other than to
point to code where things have been done that I can look at to learn
from directly.
