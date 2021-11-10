# Q: Should I use a monorepo for Kubernetes apps?

1. You have several Kubernetes infra applications and need to store them
   * Some are in Helm charts
   * Some are in modified Helm charts
   * One off, custom apps and jobs, etc. (no Helm chart)
   * Some stuff might use a operator (operator framework)
   * Example of this is the *Node Feature Discovery*
1. Monorepo advantages are negated by the heterogeneous environment
   * No real interdependencies to avoid "dependency hell"
   * Actually want independent version numbers
   * Want clarity on what changed in a *specific*
   * Copying common elements of scripts is reasonable
1. Advantage of non-monorepos
   * Separation of concerns
   * Complete separate build/deployments methods
   * Avoids yet another layer of abstraction
   * Leaves critical decisions up to the separate teams
1. Tie everything together with an structured data index (meta data)
