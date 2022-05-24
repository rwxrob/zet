# Installing CoreDNS Server in Home Lab

Good 'ol DNS. It's still a thing. I setup our team DNS back in the 90s,
but I haven't looked at a DNS server offering since then. As I go
through the setup of OpenLDAP and OIDC I realize that I probably should
get a DNS server up and running first. So, what's out there to pick
from? After reviewing the latest the obvious choice became immediately
apparent: CoreDNS written entirely in Go with a plugin architecture.
I've always loved the CoreOS team an all the great stuff they have
ported to Go. Being able to read, fix, and contribute to the code base
is a huge thing for me.

    #dns
