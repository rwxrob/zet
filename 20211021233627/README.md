# Podman Solidifies My Decision About Linux for Beginners

I might hate that `systemd` won, but it clearly has and `podman` is the
*only* viable option when creating containers that need `systemd` (for
whatever reason).

The fact that `podman` officially requires Linux is not a disadvantage.
It just means that beginners will need to prioritize learning to get a
Linux machine (virtual or real) before anything else. This is probably
best anyway instead of using some sort of crutch.

Therefore, from now on, I'm no longer recommending beginners install
Docker Desktop (or Docker anything for that matter). Instead, the first
thing any beginner should do is get root access to a Linux machine under
their control. There are lots of ways to do this --- especially since
graphics are not a requirement for any of this. Here are my
recommendations in no particular order. Each requires a different amount
of work and skill to get up and running. I've listed these by how much
work is required to get started:

1. Digital Ocean or Linode (remote with `ssh`)
1. WSL2 (if you have it)
1. VirtualBox (local VM)
1. Bare Metal (it's really not that expensive)

> ⚠️
> Note that the shell for macOS is *not* Linux! It is a variation of BSD
> UNIX and *will not work*! Please, help stop the insanity and spread
> the word.

Related:

* [20210919165819](/20210919165819/) Actually, `podman` Might Be Better Than `docker`
* [20211019060642](/20211019060642/) `podman` Adds `systemd` to All Containers
* [20211021191134](/20211021191134/) Podman Actual Is Objectively Superior to Docker

Tags:

    #boost #beginners #containers #podman #docker
