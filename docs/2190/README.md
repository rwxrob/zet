# idp-certificate-authority ~= curl --cacert

Using the `users.user.auth-provider.config.idp-certificate-authority` in `~/.kube/config` is the same as providing the cert to the `curl --cacert` command in order to tell the HTTP client about the root CA to use even if the host system does not have it added.

