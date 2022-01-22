# Use `nft` and `nftables` Instead of `iptables`

Went to check the `firewall-cmd` changes to the `iptables-save` output
only to realize there didn't see to be anything specific to NFS in
there. Turns out it was changing the new netfilter tables (which can be
checked with `nft list-ruleset` (more or less `iptables -L`).

Thanks to @devicept and gang in Twitch community for pointing this out.

Related:

* netfilter/iptables The netfilter.org \"nftables\" project  
  <https://netfilter.org/projects/nftables/index.html>
