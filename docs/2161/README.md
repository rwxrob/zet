# Authentik does not support grant_type=password

Although it is deprecated and some would say dangerous, many enterprises still depend on the Oauth2 `grant_type=password` flow---particularly those backed by LDAP username and password type of logins in the IAM space. The Authentik tool unfortunately does not support this (and probably shouldn't) so it makes it unusable to emulate environments when developing and testing tools that mesh with that flow (such as `klogin` variations).
