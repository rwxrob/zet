# Using `openssl` conf files might actually be less secure

After doing the entire root CA and intermediate CA setup using nothing but `openssl` commands and the horrible files it requires with "extensions" I went and looked at some of the other options to read the source. This prompted me to realize something that might be quite obvious to others but not initially to me: TLS/SSL does not require `openssl` configuration files (`openssl` itself does). More importantly, the complexity of getting configuration files correct seems to increase the risk of getting it wrong, and if there is one thing an admin *never* wants to get wrong it is creation of certificates. It follows that `openssl` should probably only be used to *view* certificates on systems where another tool has not been installed and should likely *never* be used to create and manage certificates. This is quite counter-intuitive when considering that `openssl` is the most mature of the tools.

The most recommended alternative to `openssl` is the `cfssl` tool written in Go and maintained by the Cloudflare company. Despite my hatred for Cloudflare as a company (their entire foundation is dubious) the use of this tool seems to be the command-line standard. There are other, simpler, even GUI tools out there that make understanding certificates when learning them much easier to grok than reading the RFCs and comments in random `openssl` configuration files---especially since the RFC includes leprous extensions to the specification to make up for inadequacies in Netscape and MS certificates in the 90s (thanks Mark and Bill, you fucking idiots).