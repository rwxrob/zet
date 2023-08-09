# Fix "cannot evict pod as it would violate pod disruption budget"

This means there is probably a `HorizontalPodAutoscaler` or the `PodDistributionBudget` update and only one replica preventing the pod from being drained. Try this procedure:

1. Change `spec.minReplicas` to 2
1. Wait for additional replica to come up (on another node)
1. Change back to 1
1. Check that pod on node being blocked from drain is 'Terminating'
1. Try `drain` again and should work

