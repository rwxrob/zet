# Mounting PVC into a K8S CronJob

Key is to make sure it is in the `spec.jobTemplate.spec.template.spec` *next to* `containers` (not in it) and that the `volumeMounts` goes under `containers`.

* Kubernetes: Is it possible to mount volumes to a container running as a CronJob? - Stack Overflow  
  <https://stackoverflow.com/questions/46578331/kubernetes-is-it-possible-to-mount-volumes-to-a-container-running-as-a-cronjob>
