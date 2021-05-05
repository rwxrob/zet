# Docker Desktop Uses Network and DNS from Host

Perhaps the best thing about Docker Desktop on Windows in an enterprise
environment where you have to play around with a VPN all the time is
that Docker Desktop using the settings of this host for all of this
stuff. Ironically, WSL2 does not. In fact, WSL2 is completely unusable
with VPN enabled unless you add some PowerShell scripts. The really
ironic thing is that you will usually have installed WSL2 in order to
get a performant Docker Desktop. And you will start up WSL2 just to
start the Docker container and the container will be able to use the VPN
while the WSL2 image that started it up does not. It's really fucking
wonky, typical Microsoft.
