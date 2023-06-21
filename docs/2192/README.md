# Invalid certificate DNS/IP errors from Kubernetes

This error only happens if the OIDC provider successfully gave a token to be used in `kubectl config set-credentials --token` *and* the cluster was able to successfully connect to that same OIDC provider to validate the token *but* found that the token did *not* include the hostname or IP or the `kubectl config set-cluster prod --server` value.

> Unable to connect to the server: x509: certificate is valid for `<other CNs, IPs and names>` , not `<DNS or IP of --server>`.

Note that the error message only seems to include DNS names (not IPs) when dealing with names in the `--server` values. The IPs can be seen when viewing the cert using `openssl`.

To fix this the additional DNS entry must be added to the certificate and the API server(s) restarted.

Related:

* ssl - How can I add an additional IP / hostname to my Kubernetes certificate? - DevOps Stack Exchange  
  <https://devops.stackexchange.com/questions/9483/how-can-i-add-an-additional-ip-hostname-to-my-kubernetes-certificate/9506#9506>
* Adding a Name to the Kubernetes API Server Certificate - Scott\'s Weblog - The weblog of an IT pro focusing on cloud computing, Kubernetes, Linux, containers, and networking  
  <https://blog.scottlowe.org/2019/07/30/adding-a-name-to-kubernetes-api-server-certificate/>
