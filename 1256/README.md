# Run Docker without Docker Desktop (Java Shit)

Today my working world crashed down around me because I could no long
use Docker Desktop after a mandatory Windows upgrade and an optional
Docker Desktop upgrade. (The errors being thrown are related to the Java
UI, which just makes me hate Java even more.)

Luckily I found a work around that has you installed `dockerd` directory
(or `podman` if you like).

[[Install Docker Into WSL2 without Docker
Desktop](https://dev.to/bowmanjd/install-docker-on-windows-wsl-without-docker-desktop-34m9)]

But there's a problem related to how shitty Windows is. I have been
benefiting from the fact that Docker Desktop runs in the memory and
network space of the host Windows OS. This means all the Cisco
OpenConnect VPN stuff works for any containers fun from within it. But
when running the `dockerd` from within a WSL2 instance, it is subjected
to the know bugs related to firewalls blocking outbound connections (for
which there is a huge issue thread on GitHub). There is a complicated
PowerShell script you can setup to run every time you run WSL2 or make a
connection just to get Windows to do what it is supposed to do in the
first place, but who wants to do that?

Unfortunately, now I am *required* to play with the shitty Windows bug
and get that PowerShell stank all over my hands just to use `dockerd`
from within WSL2.

Have I mentioned lately how much I fucking *hate* Windows for anything
that requires I be paid to do it. It is the most unreliable steaming
pile of shit I've ever had to use. I'm so very glad I had this reminder.
I was actually talking absolute nonsense before about having a Docker
image as a workspace but, silly me, I assumed Docker would work reliably
on Windows. How could I be so stupid?
