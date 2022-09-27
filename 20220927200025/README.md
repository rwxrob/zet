# Docker Uses 172.17/16, So...

Just out today that Docker uses one of the "safe" 172 subnets removing
the premise that "nothing will conflict with 172" making 192.168/16 a
better option for home networking in order to avoid conflicts with both
Docker and potentially VPNs that almost always use 10/24.

