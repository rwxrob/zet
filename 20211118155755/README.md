# K8SAPP GitHub Repo Structure (Helm)

These are my preferences. Flavor to your own taste.

## Fetch

1. Name the repo `k8sapp-<somethingshort>`
1. Create a `README.md`
   1. Title is `K8SAPP: <long name>`
1. Create a `helm` directory and change into  
   `mkdir helm && cd helm`
1. Add add the remote repo to helm with same short name
   `helm repo add somethingshort https://...`
1. Update the helm repo  
   `helm repo update`
1. List all the charts  
   `helm search repo somethingshort -l`
1. Pull the chart tarball down locally   
   `helm pull somethignshort/<TAB>`
1. Untar but add the version suffix  
   `tar xvf thechart.tgz && mv thechart thechart-0.9.0`
1. Cache chart list to detect newer versions during *Check*  
   `helm search repo shortname -l -o yaml > charts.yaml`

## Validate

1. Understand the README.md in the chart
1. Understand the Chart.yaml file
1. Understand the values.yaml file
1. Peruse the default Kubernetes resource files  
   `helm template shortname .`
1. Be aware of the template directory

## Check

1. Update the repo  
   `helm repo update shortname`
1. Check for new chart additions  
   `helm search repo shortname -l -o yaml | diff charts.yaml -; echo $?`

