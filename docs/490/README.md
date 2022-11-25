# Using Keycloak, Boring But Stable

The more research I do the more it is learn that OpenLDAP + Keycloak
(written in Java, *gag*) is the de facto standard for people doing their
own on-prem Kubernetes architectures, whether they be in a home lab, for
a small company, or a multi-national HPC ML enterprise (like my job).
There are lots of alternatives, but none offer the breadth of
integration that Keycloak currently offers (so far as I can tell). Most
importantly, Keycloak has a well supported plugin for OpenLDAP and
Kubernetes integration and anyone can write plugins for Keycloak so that
other applications can use it as an OIDC provider. One advantage of
using something old and boring and bloated for IAM stuff is that it is
so widely deployed that it is far more secure than the new stuff and
insecurities and bugs are quickly corrected given the critical nature of
it to so many billion-dollar companies.

* What is the OAuth 2.0 Authorization Code Grant Type? \| Okta Developer  
  https://developer.okta.com/blog/2018/04/10/oauth-authorization-code-grant-type

    #iam #k8s
