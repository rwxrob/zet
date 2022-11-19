# /etc/hosts add tab completion to ssh command

Normally, I'd say to setup your own DNS server at home. But I randomly
ran into an advantage of using /etc/hosts to contain local host IP
mappings to their names instead: tab completion. After typing ssh and
then pressing tab you get all the hosts from your ~/.ssh/config and
everything from your hosts file. Such is not the case if you simply use
DNS.
