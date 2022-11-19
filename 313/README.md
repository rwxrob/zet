# ZetDaemon

The *ZetDaemon* refers to the `zetd` process started into the background
by the `zet daemon` command. 

> ⚠️
> When looking for the `zetd` running processes on some systems it may
> still appear as just `zet` because the OS does not allow the renaming
> of a running process. All UNIX and Linux-based OSes do allow for this,
> however.

This process is responsible for the following:

* Calling `generate` script if configured and found
* Rendering `README.md` as `index.html` if configured
* Updating `$ZETDIR/dex/` indexes on change events
* Sending any notifications 
* Maintaining in-memory cache and indexes
* Answering API queries

> 🤬
> Don't even *think* of asking to change the name to "service" or some
> shit because of the religious sensitivity of the word "daemon". In
> fact, you can fuck right off and die. These are *daemons* and always
> have been. Get the fuck over it.

Eventually, the daemon will be containerized and the `zet` command line
interface simplified to a glorified `curl` just making API calls. This
will eventually enable the publication of live zettelkasten services
including through Kubernetes.

Also see:

* [20210814193933](/20210814193933/) ZettelRepo Sizing Estimates

