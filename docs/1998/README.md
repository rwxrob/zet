# Kubernetes CronJob considerations

The biggest thing to remember is that a CronJob is a Job on a UNIX-like schedule and requires its own container instantiation for every run. This also means that if you want it to do anything that another Deployment can see that you *must* have a PVC as well.

Also, be careful to use the right `apiVersion` (which has changed a bit over the years).

* A beginner\'s guide to Kubernetes Jobs and CronJobs \| Opensource.com  
  <https://opensource.com/article/20/11/kubernetes-jobs-cronjobs>
