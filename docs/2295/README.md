# Monitoring Kubernetes CoreDNS

(Here are some great tips handed over by ChatGPT.)

By following these steps, you should be able to monitor CoreDNS within Kubernetes and ensure that DNS delegation is happening correctly.

To monitor CoreDNS within Kubernetes and ensure the delegation of DNS lookups is happening correctly, you can follow these steps:

## Check CoreDNS Pod Status

Use the following command to check the status of the CoreDNS Pods within your Kubernetes cluster:

```sh
kubectl get pods -n kube-system -l k8s-app=kube-dns
```

Ensure that all CoreDNS Pods are in the "Running" state.

## Validate CoreDNS ConfigMap

CoreDNS configuration is maintained through a ConfigMap. Check if the ConfigMap is correctly configured by running:

```sh
kubectl get configmap coredns -n kube-system -o yaml
```

Verify that the configuration includes the desired DNS delegation settings.

## Verify DNS Delegation

To validate if DNS delegation is working correctly, you can perform DNS queries using the `dig` command within a temporary Pod:

```sh
kubectl run -i --rm --restart=Never digger --image=tutum/dnsutils --command -- bash
```

Once inside the pod, execute the following command to verify DNS delegation:

```sh
dig <domain-name>
```

Replace `<domain-name>` with the actual domain name you want to resolve. Check if the query response is as expected. Ensure that the delegation for this domain is correctly configured in CoreDNS.

## CoreDNS Metrics

CoreDNS provides metrics which can be used for monitoring. You can access the metrics endpoint by port-forwarding or using a monitoring tool like Prometheus. To port-forward the CoreDNS metrics, run the following command:

```sh
kubectl port-forward -n kube-system svc/coredns 9153:9153
```

Now, you can access the CoreDNS metrics at `http://localhost:9153/metrics`. These metrics can help you identify any issues related to DNS delegation.

## Monitoring Tool Integration

If you have a monitoring system like Prometheus set up, you can configure it to scrape the CoreDNS metrics endpoint. This allows you to create alerts and dashboards specific to CoreDNS and monitor the delegation of DNS lookups continuously.

