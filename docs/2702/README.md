# Essential HPC ML SRE OPs technologies to know in 2024

This list is biased toward the needs of huge-scale, deep-pocket, multi-national companies with the budget to purchase or rent several hundred V100 GPUs for their HPC ML needs (and pay HPC ML SREs very well to take care of them and facilitate applications that leverage that expensive infrastructure in the most economically way)..

* Linux (Red Hat, Ubuntu)
* Bash scripting
* Linux containers with Podman
* Git
* GitHub (Actions, `gh` command line tool)
* Go programming 
* Go command-line utilities (Cobra)
* Go API programming---especially the very unsexy Gin
* `goreleaser` for tagged automated releases
* Go vendoring approach to avoid problems with GHEC "inner source" model
* Kubernetes
* Harbor
* Vault
* Ansible
* Graphana
* Elastic Search
* Prometheus
* Enough Python to do Ansible and talk to ML people
* Enough Perl and Java to modernize old OPs APIs
* KVM
* QEMU
* PBC (batch processing)

Cloud isn't included because most signifiant companies have realized any HPC applications deployment is way to expensive to deploy to any cloud.

