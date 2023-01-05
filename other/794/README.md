# OIDC Setup for Kubernetes klogin

So as long as you tell Kubernetes what OIDC providers are allowed
apparently you can use any OIDC provider there is. For example, GitHub
is an OIDC provider, so you could even setup your local cluster to allow
logins to your local cluster.

I wonder if having a generic `oidc` Bonzai branch would be able to cover
all the different ways to save the token. I mean, all the cached
variables would be the same and other branch commands could access the
same variables via the `vars` branch. I think that is the way to do
because OIDC is so universal. It's the equivalent to the `auth-go` stuff
I made before that just worked for any three-legged authentication
(which I think I could have replaced with OIDC, by the way).

