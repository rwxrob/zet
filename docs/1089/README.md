# K8SAPP Helm Procedure

These are my preferences for an air-gapped organization. Flavor to your
own taste.

## Fetch

1. Name the repo `k8sapp-<somethingshort>`
1. Create a `README.md` with title `K8SAPP: <long name>`
1. Create a `helm` directory and change into  
1. Add remote repo to helm with same short name
1. Update the helm repo  
1. Pull the chart tarball down locally   
1. Pull and cache the `index.yaml` file to detect changes later

## Validate

1. Understand the README.md in the chart
1. Understand the Chart.yaml file
1. Understand the values.yaml file
1. Understand the template directory
1. Peruse the rendered Kubernetes resource files  
   `helm template shortname . > /tmp/shortname.yaml`
1. Identify and download all image dependencies *locally*
1. *Locally* scan images for security compliance and dependencies
1. Ensure clean legal FOSS pedigree

## Configure

1. Strongly document any changes to the template *itself*
1. Pushed validated images to private registry

## Check

1. Update the repo  
   `helm repo update shortname`
1. Check for new chart additions  
   `helm search repo shortname -l -o yaml | diff charts.yaml -; echo $?`

