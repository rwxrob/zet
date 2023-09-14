# Allow access to group of users with Istio OAuth2

Overall Flow:

1. Incoming Request
1. Istio Ingress Gateway
1. Authorization Policy
1. Oauth2-Proxy
1. If (authorized) Application Service
1. Else Rejected Unauthorized

Related:

* Authenticating and Authorizing end-users with Istio and Auth0  
  <https://auth0.com/blog/securing-kubernetes-clusters-with-istio-and-auth0/>
* Istio / External Authorization  
  <https://istio.io/latest/docs/tasks/security/authorization/authz-custom/>
* Configuring Istio with OIDC authentication - Homelab.blog  
  <https://homelab.blog/blog/devops/Istio-OIDC-Config/>
* Istio External OIDC Authentication with OAuth2-Proxy \| Medium  
  <https://medium.com/@lucario/istio-external-oidc-authentication-with-oauth2-proxy-5de7cd00ef04>
