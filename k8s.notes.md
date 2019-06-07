## Install

### Install `minikube`

https://kubernetes.io/docs/tasks/tools/install-minikube/
*  `brew install kubernetes-cli`
*  `brew cask install minikube`
*  `minikube start`

## Working with K8s

### Create a deployment

GCR:  
`kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node`
DockerHub:  
`kubectl create deployment scratchy-node --image=registry.hub.docker.com/inovakov/scratchy`

Or, if you have the image installed locally:  
`kubectl create deployment scratchy-node --image=inovakov/scratchy`

### Create a service (so you can talk to the pod)

`kubectl expose deployment scratchy-node --type=LoadBalancer --port=3000`  
* `--type=LoadBalancer` means "expose outside of the cluster"
* the port number you give here is the port on which the service in the container is listening

Remove it (un-expose): `kubectl delete service scratchy-node`

Tell minikube to expose it as well: `minikube service scratchy-node`

### Inspect

`kubectl get deployments`  
`kubectl get pods`  
`kubectl get events`  
`kubectl config view`  
`kubectl get services`  

### Cleanup

`kubectl delete service scratchy-node`  
`kubectl delete deployment scratchy-node`  

`minikube stop`  
`minikube delete`  
