# Use 198.18/15 for Home Lab

The reserved subnet for RFC2544 is specifically for "benchmark testing",
and what is a homelab for if not for testing, including, but not limited
to network benchmarking. (In fact, after reading this specification I'm
interested in actually adding my own network benchmark numbers as well
some day.) This range has absolutely zero chance of ever having a
conflict with any VPN of any kind, and it also won't overlap with many
of the devices that default to 192.168.1.0/24.

What's also cool about this is that you get two /16 subnets out of this,
which works so well when emulating an air-gapped infrastructure:

* 198.18/16 - private (no Internet connectivity whatsoever)
* 198.19/16 - normal NAT Internet DHCP zone (laptops, printers, phones)

Did I mention that it is also a lot easier to include on documentation
and whiteboards?

Related:

* https://www.rfc-archive.org/getrfc.php?rfc=3330#gsc.tab=0
* https://www.rfc-archive.org/getrfc?rfc=2544#gsc.tab=0

