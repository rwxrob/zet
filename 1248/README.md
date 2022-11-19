# Mim KEG Multiple Site Support

One core requirement of KEG sites will be that they are redundant,
modeled after DNS. There will always be an authoritative source, one
primary KEG site, but there may be dozens, hundreds, thousands of
redundant copies of it. We want people creating KEG sites to be sure
they are never silenced by simply taking down one part of the Internet
-- or even all of the Internet. We also want to be able to change which
KEG site is authoritative very easily, with one `mim keg auth main`
command.

The only thing I know for sure at this moment about implementation
design is that everything will be signed with GPG and that all metadata
about the current version and authoritative source will be in `/KEG`.

Every KEG site will run the `mim keg serve` command which doubles as a
monitor for the current data that it is serving. If it ever changes, the
process will look at a localized configuration file that is pointing to
it's upstream paired KEG nodes and push to them as well. The
configuration of paired KEG nodes will never reside on any single server
so that if one is compromised all would have to be traced to see what
servers they pair to. This ensures a secret network of replicated KEG
master nodes.

Replication can happen using any of a number of supported methods
including `rsync`, `scp`, `ftp`, `telnet`, `http`, `gRPC`, and our own
internal protocol tunneling through port 80. There is no concern
whatsoever for the security of the transport. In fact, encrypting the
tunnel has always been a fucking stupid idea. Encrypting and signing the
data itself is far more sustainable and secure. You can print it on
paper and scan it in from another country if needed (which is how the
RSA algorithm escaped America). Or, you can have one paired KEG site
device mounted to several copies of USB drives that are regularly
delivered to human assets on the ground (bus drivers headed into dark
zones, etc.). Whatever it takes to disseminate and ensure redundancy of
the knowledge on any give KEG site.

To accomplish this level of KEG (which won't come for a year probably)
we'll build on the GPG signing of content including the meta stuff in
`/KEG`. GPG will be the basis of authentication. It is perhaps the
single biggest thing missing from the modern Web. No one has any fucking
idea if someone even actually said what is claimed. By making every
individual resource in a KEG site just a file we can sign and cache the
signatures for every fucking thing in the entire KEG site. It isn't that
much overhead because we only need to sign when something is created or
changed. When and if we need to change GPG signatures, we just re-sign
all the resource and propagate. This is why database-driven Web
architectures are so FUCKING stupid (and easy to own). Developers of
such shit can never dream of being able to accomplish this level of
shared redundancy, sustainability, while not sacrificing any security or
authenticity. (I suppose those idiots working at places like Netscape,
Sony, and Equi-fucking-fax, will just keep giving us more data to, um,
share.)

GPG also allows a certain level of obfuscation because some sites might
choose to encrypt as well so that only members with the public key (only
given to certain members) could see it, not a hard level of security,
just for obfuscation. That would completely shut down most nefarious,
marketing driven search engines from ever even indexing the content.

    #mim #keg #gpg #decentralization
