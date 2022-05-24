# Kubernetes kubeconfig grant_type=password Deprecated?

Okay, so the OAuth2 page has this rather dire warning about the most common way to use OIDC providers for Kubernetes currently:

> The Password grant type is a way to exchange a user's credentials for an
access token. Because the client application has to collect the user's password
and send it to the authorization server, it is not recommended that this grant
be used at all anymore.
>
> This flow provides no mechanism for things like multifactor
authentication or delegated accounts, so is quite limiting in practice.
> 
> The latest OAuth 2.0 Security Best Current Practice disallows the
password grant entirely.

Where does this leave LDAP-driven `grant_type=password` authorization flows such as those used by enterprises everywhere in their `klogin` programs? These flows just pull down the tokens needed using one query and store the token for use in kubeconfig

* OAuth 2.0 Password Grant Type  
  https://oauth.net/2/grant-types/password/

    #k8s
