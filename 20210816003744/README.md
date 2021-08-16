# Make Sure `/etc/sshd_config`, Not `/etc/ssh_config`

So I'm working on debugging a problem that takes looking at the
kubelet logs only to discover the following error trying to `ssh` from
one of the head nodes:

    /etc/ssh/ssh_config: line 53: Bad configuration option: allowtcpforwarding
    /etc/ssh/ssh_config: terminating, 1 bad configuration options

You can figure out what happened for sure. But looking at the
`/etc/ssh_config` file gives it away:

    AllowTcpForwarding yes

How is that a give away? Because it's a fucking server (`sshd`)
configuration setting, not client.

The real shame of this is that it got added to a chef script and got
pushed to every fucking node in the cluster. Thank God I didn't do it.

Ironically, I immediately noticed it as the problem because I have color
enabled from my terminal and `vim` from these systems all supports color
syntax hilighting. The `AllowTcpForwarding` was white, not colored like
the other directives. Anyone with a color terminal would have
immediately spotted this problem. But pretty much every single opers
person, and my entire team of peer "infrastructure engineers" (except
one) still use Putty, which is only black and white for them. That's
right, I have my first enterprise outage example of when color would
have saved the day (and why Putty fucking sucks).
