# Ticketing Dashboard

## Setup

* Install [Grafana via Helm](https://github.com/helm/charts/tree/master/stable/grafana).

## Prometheus

* Access Prometheus via [http://localhost:9090](http://localhost:9090):

```bash
$ kubectl --namespace monitoring port-forward $(kubectl get pod --namespace monitoring -l prometheus=kube-prometheus -l app=prometheus -o template --template "{{(index .items 0).metadata.name}}") 9090:9090
Handling connection for 9090
```

## Grafana

* Access Grafana via [http://localhost:3000](http://localhost:3000):

```bash
$ export POD_NAME=$(kubectl get pods --namespace default -l "app=grafana,release=grafana" -o jsonpath="{.items[0].metadata.name}")
$ kubectl --namespace default port-forward $POD_NAME 3000
Handling connection for 3000
```

* Get Password

```bash
$ kubectl get secret --namespace default grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
...
```