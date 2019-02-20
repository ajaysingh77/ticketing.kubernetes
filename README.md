# Ticketing.Kubernetes

## TL;DR

Blog post is currently being written, access to code base for microservices can be found:

* [Ticketing.Web](https://github.com/denhamparry/ticketing.web)
* [Ticketing.API](https://github.com/denhamparry/ticketing.api)
* [Ticketing.Worker](https://github.com/denhamparry/ticketing.worker)
* [Ticketing.Data](https://github.com/denhamparry/ticketing.data)

## Setup

* Setup 'cert-manager'

> TODO: Include Helm setup

```bash
$ kubectl apply -f cert-manager
```

* Setup 'ticketing.api'

> TODO: Add AKS domain script from 'providers/aks/'

```bash
$ kubectl apply -f configmap.yml
configmap/ticketingapi-configmap created
$ kubectl apply -f secret.yml
secret/ticketingapi-secret created
$ kubectl apply -f deployment.yml
deployment.apps/ticketingapi created
$ kubectl apply -f svc.yml
service/ticketingapi created
```

## Status

### Minikube

> TODO: Create local minikube documentation

```bash
$ minikube service ticketingapi
Opening kubernetes service default/ticketingapi in default browser...
```

## Delete

> TODO: Add 'helm list' deletion method.

```bash
$ kubectl delete -f ticketing.api
```
