# Make Best Use of 192.168/16 Subnets

After refreshing my memory on subnet architecture (and having a friend
catch an overlap in my subnets even though I have a VLAN separation) I
happened upon the following rather obvious pattern that tranches up the
ever popular 192.168/16 subnet in a way that the gateway always ends in
.1 and the last IP is always a .254 (not counting the broadcast IP
.255). This makes for very clean boundaries and eight subnets of every
specified size:

CIDR                                           | Every | IPs/Subnet
192.168.{0,1,2,3,4,5,6,7}.0/24                 | 1     | 254
192.168.{8,10,12,14,16,18,20,22}.0/23          | 2     | 510
192.168.{24,28,32,36,40,44,48,52}.0/22         | 4     | 1022
192.168.{56,64,72,80,88,96,104,112}.0/21       | 8     | 2044
192.168.{128,144,160,175,191,207,224,240}.0/20 | 16    | 4094

Of course, these can be grouped entirely differently, on different
boundaries, but this is nice to just grab one of a given size that you
know starts and stops on a reasonable number.

Related

* https://networkcalc.com/subnet-calculator
