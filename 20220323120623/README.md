# Plain Binaries or Installer Packages?

I'm a bit torn as to what is the best way to manage and produce a
distribution given how easy it is to embed everything into a Go binary
these days. I'm very inclined to never do anything with package
management ever again. Between the AutoUpdate approach, and the
AutoUpdatePrompt option I can't see a need to ever have anything else
travel with the application itself. Either it gets embedded or it is
something that can be pulled from the Internet. No need for an MSI or
mac ISO pkg. Just the binary itself. The operating system will remind
people they need to move the program to the place it belongs. In fact,
the hardest part of this is getting the users to allow their computers
to safely download raw executables from the Internet, a major security
problem even today.

> I can conceive of a `bonzai` command that would do that downloading
> with the user prompts for validation and such. I had not planned it
> that way, but `bonzai` could easily become an "application manager"
> (building on the idea of package managers from days past). The
> assumption would be that Bonzai applications are *always* entirely
> self-contained or able to get what they need from the network. 

The only pause I have is when thinking about enterprise applications.
Say I release an open source tool that automatically phone's home with a
prompt to be updated (like `gh` does). What does that say about
corporate security policies with regard to software installation?
Technically, if I accept the `gh` self-updater I'm in violation os
several companies policies. I've by-passed any vetting of that software
at all. But the world seems ready for "evergreen" software distribution
where the control over the security and updated-ness of the app lies
with the develop of the app and not through some overburdened,
gate keeper who wouldn't even know what to look for in the first place.

Could the future of IT architecture be the combination of "zero-trust"
plus self-updating applications with no package management at all? For
many Go applications this is very doable right now. In fact, Go is just
following a "network install" situation that most Linux distros have
been leveraging for years, decades even. Everyone downloads the
light-weight version of the distro and sits back while it network
downloads and installs everything that is most recent. Again, in
enterprise land that isn't something people do, or at least didn't used
to do. But the future is bright and full of opportunity for these kinds
of freedoms without sacrificing security.

    #golang #packaging #release #distribution #apps
