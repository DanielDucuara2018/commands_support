# Kubernetes Overview

## CRUD Commands

```sh
kubectl create deployment [NAME] image=[IMAGE] [OPTION1] ...# create deployment
kubectl delete deployment [NAME]
kubectl edit deployment [NAME]
kubectl get deployment [NAME]
```

## Status of differents K8s components

```sh
kubectl get nodes 
kubectl get pod
kubectl get services
kubectl get replicaset
kubectl get deployment
```

## Debugging pods

```sh
kubectl logs [POD_NAME]
kubectl exec -it [POD_NAME] --bin/bash
kubectl describe pod [POD_NAME]
```

## Debugging services

```sh
kubectl describe service [SERVICE_NAME]
```

## Run a kubernetes manifest file

```sh
kubectl apply -f [FILE] # create and configure 
kubectl delete -f [FILE] # delete
```