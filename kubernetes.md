# Kubernetes

## Concepts

- Pod
  - A related group of running containers.
- Deployment
  - A managed deployment of one or more pod instances. Manages replica count.
- Service
  - A pointer to the pods in a deployment. Updates as pod instances are hot-swapped or scaled up and down.

## Kubectrl

`kubectrl` is the cli tool for managing and interacting with a Kubernetes cluster.

### Examples

`kubectl create -h`
`kubectl apply -f ./moneypenny`
`kubectl scale nginx --replicas=0`
`kubectl get services`
`kubectl get deployments`
`kubectl create secret generic moneypenny-secret --from-literal=KEY=VALUE`
`kubectl logs event-store-173223513-9dm94`
`kubectl describe pod event-store-173223513-9dm94`
