# Starting the kutil project

At work we have a tool that does a lot of things that are missing from any existing Kubernetes tool or endpoint API call. It's no surprise. Kubernetes is just one big cluster-fuck of a project really (just look at the kubectl code to handle something as simple as the `~/.kube/config` file). Doesn't matter. Kubernetes is the law of the land.

My `kutil` project will largely just be for stuff I want to consolidate and I can do that with my Bonzai module in a way that allows all the subcommands to be consolidated in different ways by others. Plus most people will keep using the incredibly obtuse Cobra module in their projects. That's fine. Not me.

Even though the project will contain subcommands that are identical to those I have at work---some of which I wrote---writing them from scratch for `kutil` should be fine. These are entirely different because the Cobra versions I was forced to create all have `--shit` in them. I want to create a *good* domain specific language related to Kubernetes than *has zero dashes*.

I'm glad to have yet another project that allows me to maintain Bonzai and show just how superior it is for those who want clear, concise command interfaces.

