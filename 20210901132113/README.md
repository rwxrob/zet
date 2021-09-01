# Docker Desktop for Business No Longer Free

Well this sucks. I use Docker Desktop every day and have had a hard time
convincing my company that using Docker Desktop is even worth having a
'non-standard' application installed onto Windows. Yet my company has no
official plan to put Linux on any workstation or laptop. That leaves me
with three alternatives:

1. Just keep quiet about it
2. Find an alternative that does about the same things
3. Use WSL2 alone and deal with VPN issues

Purchasing a 'business' license is out of the question. They won't even
consider it.

This is a huge deal for me because I discovered the happy coincidence
that running a workspace container in Docker Desktop enjoyed all the VPN
routing and magic of any other application running on Windows. WSL2 does
not, meaning that without a shit-ton of customization in PowerShell I
cannot even connect to our environment with WSL2.

I already went down the road of installing `docker` directly into WSL2,
which obviously still has all the same VPN problems because it is
running within WSL2's network.

This also raises the question of whether I should even rely on Docker
Desktop for the Beginner Boost. Do I want to create a dependency in new
learners on something they might never be able to use in their working
environments? Then again, most would also not be able to install Linux
onto their work laptops, which leaves WSL2 (raw) or a virtual machine,
which is always a pain in the ass.

For now I am required to just do option \#1 while I figure everything
out.

Related:

* [20210901132113](/20210901132113/) Docker Desktop for Business No Longer Free
* [20210701190237](/20210701190237/) Windows Docker Desktop is Torture, Gimme Linux
* [20210701195103](/20210701195103/) Run Docker without Docker Desktop (Java Shit)
* [20210702142020](/20210702142020/) Docker Desktop Fatal .NET Error
* [20210713162404](/20210713162404/) Just Use Docker Desktop
* [20210721030557](/20210721030557/) Will you be starting with Docker Desktop approach?
* [20210721032040](/20210721032040/) Can I Run Linux Desktop in Containers?
* Reddit: Docker Desktop (Windows) Alternatives?
  <https://www.reddit.com/r/docker/comments/pfo6gm/docker_desktop_windows_alternatives/>

Tags:
    #docker #enterprise #news
