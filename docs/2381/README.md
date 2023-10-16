# Latest podman default image size increased to 100 GB

I struggled with an old `podman` version on my Mac that couldn't build a simple SSH image because it kept running out of space on the `/sysroot` directory mount. I upgraded `podman` and (finally) figured out to completely `podman rm` the previous machine to create another new one with `podman init` and it was able to do it without any other changes.
