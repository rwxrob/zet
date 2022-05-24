# Learn OAuth2 and OIDC

I cannot stress enough how important it is to completely master OAuth2
(authentication) and OIDC (authorization). Ever substantial application
on the planet is using these technologies today including Kubernetes.
This is the key to being able to create a command line application that
authenticates to something else without problem. The days of things like
LDAP or AD or NIS are way over (even though LDAP and AD are usually
backing up the OIDC stuff in some way, with Keycloak for example).

OIDC is the best "single sign-on" practice for both the Internet and
private internal enterprise authentication, and the fact that the same
tech works inside or outside a VPN is what leads to the future of
zero-trust deployments.

* OpenID Connect explained \| Connect2id  
  https://connect2id.com/learn/openid-connect

* Twitch OIDC Authentication  
  https://dev.twitch.tv/docs/authentication/getting-tokens-oidc/

* https://www.digitalocean.com/community/tutorials/recommended-steps-to-secure-a-digitalocean-kubernetes-cluster#step-1-enabling-remote-user-authentication

    #oidc
