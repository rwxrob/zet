# Use bitnami Helm charts even if not main

So looks like Bitnami actually adds stuff to their Helm charts that make them more desirable than just the plain one. Let's compare the popular Harbor chart for example. The `goharbor` one just has the following images included:

```
image: goharbor/harbor-core:v2.11.1
image: goharbor/harbor-jobservice:v2.11.1
image: goharbor/harbor-portal:v2.11.1
image: goharbor/registry-photon:v2.11.1
image: goharbor/harbor-registryctl:v2.11.1
image: goharbor/harbor-db:v2.11.1
image: goharbor/harbor-db:v2.11.1
image: goharbor/redis-photon:v2.11.1
image: goharbor/trivy-adapter-photon:v2.11.1
```

While the Bitnami one includes a full Redis and PostgreSQL setup in a batteries-included sort of way.

```
image: docker.io/bitnami/harbor-core:2.11.1-debian-12-r5
image: docker.io/bitnami/harbor-core:2.11.1-debian-12-r5
image: docker.io/bitnami/harbor-jobservice:2.11.1-debian-12-r4
image: docker.io/bitnami/harbor-jobservice:2.11.1-debian-12-r4
image: docker.io/bitnami/nginx:1.27.1-debian-12-r4
image: docker.io/bitnami/nginx:1.27.1-debian-12-r4
image: docker.io/bitnami/harbor-portal:2.11.1-debian-12-r4
image: docker.io/bitnami/harbor-portal:2.11.1-debian-12-r4
image: docker.io/bitnami/harbor-registry:2.11.1-debian-12-r5
image: docker.io/bitnami/harbor-registryctl:2.11.1-debian-12-r4
image: docker.io/bitnami/harbor-registry:2.11.1-debian-12-r5
image: docker.io/bitnami/harbor-registryctl:2.11.1-debian-12-r4
image: docker.io/bitnami/postgresql:13.16.0-debian-12-r9
image: docker.io/bitnami/redis:7.4.0-debian-12-r2
image: docker.io/bitnami/harbor-adapter-trivy:2.11.1-debian-12-r2
image: docker.io/bitnami/harbor-adapter-trivy:2.11.1-debian-12-r2
```

Needless to say, this makes a huge difference when creating K8SAPP repos and setting them up for regular updates and installations.
