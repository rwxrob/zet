# Kubernetes Colearning, Nov 6, 10:30am

📺 <https://youtu.be/SoVJlP2kdfw>

* Still using Node Feature Discovery as example
* Realized we really should install private registry first
* Decided on Harbor but will to install in other video

Steps to install:

1. Identify the Helm chart
1. Create an internal git repo to contain the Helm chart
1. Download and decompress the Helm chart (tar) into repo
1. Commit the repo with a pristine version of the chart
1. Create an initial empty values.yaml (at same level)
1. Put *only* overlay changes into the new values.yaml file
1. Scan the default chart for images that must be imported internally
1. Download, vet, and install images chart requires in private registry

Related:

* <https://kubernetes-sigs.github.io/node-feature-discovery/stable/get-started/index.html>
* <https://github.com/rwxrob/lab-k83-node-feature-discovery>
