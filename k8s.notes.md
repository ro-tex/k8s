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

### Check it out

`kubectl get deployments`
`kubectl get pods`
`kubectl get events`
