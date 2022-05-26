# Authenticating and Authorizing Kubernetes

Just logging in to a Kubernetes cluster is one of the biggest problems
of the entire project. Since all the cloud providers have their own
methods of doing this and provide that out of the box, not having a
login method at all is the first major missing piece of any on-prem
Kubernetes deployment (along with other things like Ingres, CNI, storage
classes, etc.).

Using an OIDC provider is by far the most common architecture (yes, even if you are using a home lab setup wijth OpenLDAP and Keycloak, dex, or Vault).

> 1. Login to your identity provider
> 2. Your identity provider will provide you with an access_token,
>    id_token and a refresh_token
> 3. When using kubectl, use your id_token with the --token flag or add
>    it directly to your kubeconfig
> 4. kubectl sends your id_token in a header called Authorization to the
>    API server
> 5. The API server will make sure the JWT signature is valid by checking
>    against the certificate named in the configuration
> 6. Check to make sure the id_token hasn't expired
> 7. Make sure the user is authorized
> 8. Once authorized the API server returns a response to kubectl
> 9. kubectl provides feedback to the user

It can pull this off because it keeps other authentication stuff "on file" for
the service account that matches the name from the `id_token`. But most
importantly (and counter-intuitively) Kubernetes *does not use the
access_token* for anything. That's right. It completely ignores it. 

> Since all of the data needed to validate who you are is in the id_token,
> Kubernetes doesn't need to "phone home" to the identity provider. In a
> model where every request is stateless this provides a very scalable
> solution for authentication. It does offer a few challenges:
>
> 1. Kubernetes has no "web interface" to trigger the authentication
>    process. There is no browser or interface to collect credentials
>    which is why you need to authenticate to your identity provider
>    first.
> 2. The id_token can't be revoked, it's like a certificate so it should
>    be short-lived (only a few minutes) so it can be very annoying to
>    have to get a new token every few minutes.
> 3. To authenticate to the Kubernetes dashboard, you must use the
>    kubectl proxy command or a reverse proxy that injects the id_token.

If you have done any coding with OAuth2 before this will seems really weird,
but you'll come to be very grateful because it means that using
`grant_type=authorization_code` doesn't mandate a complicated, web-based
redirection. And since things like Hashicorp Vault *only* to
`authorization_code` (instead of `password`) `grant_type` your command-line
`klogin` tools will still work (in theory, I'm confirming this right now).

* Authenticating \| Kubernetes  
  https://kubernetes.io/docs/reference/access-authn-authz/authentication/

    #k8s #auth #tips
