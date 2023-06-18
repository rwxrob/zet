# OIDC Resource Owner Password Flow (`grant_type=password`)

This flow is "deprecated" and not even included in OAuth2.1 but is still a critical part of most enterprise authentication strategies where the control of *both* the application front end and back end are controlled entirely by that enterprise. The argument that username and password is an "anti-pattern" is almost entirely built on the risk of the "client" (front end, binary) being untrusted. This argument collapses when that control is gauranteed.

* api - OAuth2 Password Grant vs OpenID Connect - Stack Overflow  
  <https://stackoverflow.com/questions/47447755/oauth2-password-grant-vs-openid-connect>
* Resource Owner Password Flow with OIDC  
  <https://auth0.com/docs/authenticate/login/oidc-conformant-authentication/oidc-adoption-rop-flow>
