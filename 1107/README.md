# Beware of Cisco ACI and Kubernetes

Turns out that [Cisco ACI] has been causing major issues for us at work
in production. The default configuration effectively ignores ARP the way
most expect it to work. And since Kubernetes messes with IP assignment
so much, including multiple IPs pointing to a single machine address,
having the defaults can really fuck you up. ACI means well. It's trying
to handle things magically by looking at packets and doing the right
thing instead of waiting around for the ARP requests, which can add
unnecessary latency, but in this case the magic really ruins your day.
If you are seeing ARP issues in your Kubernetes network, question number
one might be "Do we use Cisco ACI and how is it configured?"

[Cisco ACI]: <https://www.sdxcentral.com/data-center/definitions/what-is-cisco-aci/>

