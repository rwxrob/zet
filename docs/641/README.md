# Add This to Enable DaemonSets on Control Plane Nodes

```yaml
    spec:
      tolerations:
      # these tolerations are to have the daemonset runnable on control plane nod
es
      # remove them if your control plane nodes should not run pods
      - key: node-role.kubernetes.io/control-plane
        operator: Exists
        effect: NoSchedule
      - key: node-role.kubernetes.io/master
        operator: Exists
        effect: NoSchedule
```


