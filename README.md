# kubernetes-squid
Run Squid proxy as a service for your Kubernetes containers

Here you will find:
* Kubernetes pod descriptor with Squid container
* Kubernetes service descriptor that publishes Squid proxy port

## Pre-requisites

* Kubernetes cluster (tested with 2 nodes [Vagrant + CoreOS](https://github.com/pires/kubernetes-vagrant-coreos-cluster))
* ```kubectl``` configured to access your cluster master API Server

## Deploy

```
kubectl create -f squid-service.json
kubectl create -f squid-controller.json
```

## Validate

```
kubectl get pods
```

You should see something like this:

```
POD                                    IP                  CONTAINER(S)           IMAGE(S)                     HOST                LABELS                                       STATUS
cd6c24dc-aa34-11e4-a06e-0800272d7481   10.244.26.3         squid                  jpetazzo/squid-in-a-can      172.17.8.104/       component=squid                              Running
```