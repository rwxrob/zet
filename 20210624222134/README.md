# Simplified Command Line Interfaces Through State Caching

One of the hindrances to using simpler command lines (without a shit-ton
of dashes) is how much people feel they have to convey in a single
command. It's as if they panic that if you cannot do everything at once
then it will somehow hinder the application even though it is totally
possible by dividing up the command into several individual commands
that cache the current state of the command-line program. We are
beginning to see people realize this now in `kubectl` with `set-context`
and such. Having to type all that out every time is just too tedious. So
adding a mechanism to cache that information covers the need. This same
approach can be done with *any* command.

A good example of an otherwise create program that fails at this is
`docker`.

```
SYNOPSIS
			 docker run [-a|--attach[=[]]] [--add-host[=[]]]
       [--blkio-weight[=[BLKIO-WEIGHT]]] [--blkio-weight-device[=[]]]
       [--cpu-shares[=0]] [--cap-add[=[]]] [--cap-drop[=[]]]
       [--cgroup-parent[=CGROUP-PATH]] [--cidfile[=CIDFILE]] [--cpu-count[=0]]
       [--cpu-percent[=0]] [--cpu-period[=0]] [--cpu-quota[=0]] [--cpu-rt-period[=0]]
       [--cpu-rt-runtime[=0]] [--cpus[=0.0]] [--cpuset-cpus[=CPUSET-CPUS]]
       [--cpuset-mems[=CPUSET-MEMS]] [-d|--detach] [--detach-keys[=[]]]
       [--device[=[]]] [--device-cgroup-rule[=[]]] [--device-read-bps[=[]]]
       [--device-read-iops[=[]]] [--device-write-bps[=[]]] [--device-write-iops[=[]]]
       [--dns[=[]]] [--dns-option[=[]]] [--dns-search[=[]]]
       [--domainname[=DOMAINNAME]] [-e|--env[=[]]] [--entrypoint[=ENTRYPOINT]]
       [--env-file[=[]]] [--expose[=[]]] [--group-add[=[]]] [-h|--hostname[=HOSTNAME]]
       [--help] [--init] [-i|--interactive] [--ip[=IPv4-ADDRESS]]
       [--ip6[=IPv6-ADDRESS]] [--ipc[=IPC]] [--isolation[=default]]
       [--kernel-memory[=KERNEL-MEMORY]] [-l|--label[=[]]] [--label-file[=[]]]
       [--link[=[]]] [--link-local-ip[=[]]] [--log-driver[=[]]] [--log-opt[=[]]]
       [-m|--memory[=MEMORY]] [--mac-address[=MAC-ADDRESS]]
       [--memory-reservation[=MEMORY-RESERVATION]] [--memory-swap[=LIMIT]]
       [--memory-swappiness[=MEMORY-SWAPPINESS]] [--mount[=[MOUNT]]] [--name[=NAME]]
       [--network-alias[=[]]] [--network[="bridge"]] [--oom-kill-disable]
       [--oom-score-adj[=0]] [-P|--publish-all] [-p|--publish[=[]]] [--pid[=[PID]]]
       [--userns[=[]]] [--pids-limit[=PIDS_LIMIT]] [--privileged] [--read-only]
       [--restart[=RESTART]] [--rm] [--security-opt[=[]]] [--storage-opt[=[]]]
       [--stop-signal[=SIGNAL]] [--stop-timeout[=TIMEOUT]] [--shm-size[=[]]]
       [--sig-proxy[=true]] [--sysctl[=[]]] [-t|--tty]
			 [--tmpfs[=[CONTAINER-DIR[:OPTIONS]]] [-u|--user[=USER]] [--ulimit[=[]]]
       [--uts[=[]]] [-v|--volume[=[[HOST-DIR:]CONTAINER-DIR[:OPTIONS]]]]
       [--volume-driver[=DRIVER]] [--volumes-from[=[]]] [-w|--workdir[=WORKDIR]] IMAGE
       [COMMAND] [ARG...]
```

That's *just* the `docker run` command. Yeah, it's fucking insanely stupid.
This is the reason I hate Cobra with ever fiber of my being. It facilitated
that shit. It caused `kubectl` to have 14,000 lines of "completion" code that
must be evaluated. It's the fucking devil. It should be renamed to Satan's
Commander. No rational human being wants to see this when they look for help
documentation?

This is why the entire IT industry needs to stop thinking of command lines as
places to add year another "option" and start treating them like the grammars
they are. This is the definition of *domain specific language* so why not treat
it as such. And one of the core tenets of any grammar and language is the
ability to provide context as you communicate. Each phrase is built on the next
in a way that builds and changes context as you use simple phrases. This
linguistic reality seems absolutely foreign to developers who create shit like
this set of "options" and "switches". They are not. They are verbs and nouns
and adjectives and adverbs. The sooner we start treating them as such the
better for everyone and our human-computer interfaces will approach what Tony
Stark portrayed, natural language communication that just happens to be
textual. When Tony is asked by Jarvis, "Would you like me to build it?" he
says, "Thrill me" but because of the context Jarvis knows that means "yes".
That's how our command lines should behave as well. The first step is
eliminating the dashes and using speakable words with CmdBox. Then we can begin to
eventually apply grammar rules (through meta languages like PEGN.dev) and ultimately, as resources will eventually allow, natural language processing.

