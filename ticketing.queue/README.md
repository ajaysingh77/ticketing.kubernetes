# Ticketing.Queue

```bash
kubectl get --raw "/apis/custom.metrics.k8s.io/v1beta1/namespaces/default/pods/*/tickets" | jq .
```