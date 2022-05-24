# Using Vault Instead of Keycloak

Update: Vault does *not* support the `grant_type=password` that many
authorization flows have established despite it being discouraged by
OAuth itself. This may be the singular reason so many people are stuck
on Keycloak, because their `klogin` programs use `password`. Vault only
supports type `authorization_code`.

* Vault OIDC Token parameters  
  https://www.vaultproject.io/api-docs/secret/identity/oidc-provider#parameters-15
* What is the OAuth 2.0 Authorization Code Grant Type? \| Okta Developer  
  https://developer.okta.com/blog/2018/04/10/oauth-authorization-code-grant-type

All I had to read was that Vault is written in Go 1.17 from Hashicorp
and Keycloak is an ancient Java application from a company that was
acquired by RedHat to make my decision about an IAM provider for my home
lab. At work we are on Keycloak now, but planning on migrating off to
Vault eventually. So might as well get a jump on it.

    #iam #k8s
