# Getting Started With Kubernetes

![](pictures/kubernetes_logo.png)

- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `Kubernetes is an open source container orchestration engine for automating deployment, scaling, and management of containerized applications.`
- ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) `It groups containers that make up an application into logical units for easy management and discovery.`
- ![#1589F0](https://placehold.it/15/1589F0/000000?text=+) `Kubernetes is a container orchestration system for Docker containers that is more extensive than Docker Swarm and is meant to coordinate clusters of nodes at scale in production in an efficient manner.`

## REQUIREMENTS:


- You should have good knowledge of docker to get hands on [kubernetes](https://kubernetes.io/).
- It is good to have [Linux](https://www.linux.org/) OS.
- Have [Docker](http://docs.docker.com/engine/installation/) Installed.
- Have an account on [Docker Hub](https://hub.docker.com)

    
## Creating, Running, and Sharing a Container Image:

### Building the container image:

```
- Creating a trivial Node.js app
- Creating a Dockerfile for the image
- Building the container image
```
### Command:

```
$ docker build -t kubia .
```
![](pictures/docker_1.png)

## Running the Container Image:
```
$ docker run --name kubia-container -p 8080:8080 -d kubia
$ ping http://localhost:8080
    You’ve hit 44d76963e8e1
```
## Pushing the Image to an Image Registry:

```
$ docker tag kubia khawajaosama/kubia
$ docker push khawajaosama/kubia
```
## Setting Up A Kubernetes Cluster:

The simplest and quickest path to a fully functioning Kubernetes cluster is by using
Minikube. Minikube is a tool that sets up a single-node cluster that’s great for both
testing Kubernetes and developing apps locally.

### Running a local single-node Kubernetes cluster with Minikube:
```
$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.23.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```
### Starting a Minikube Virtual Machine:

```
$ minikube start
Starting local Kubernetes cluster...
Starting VM...
SSH-ing files into VM...
...
Kubectl is now configured to use the cluster.
("It will take 5-6 min, depends on your configuration so dont panic, mine laptop took 10 mins")
```
### INSTALLING THE KUBERNETES CLIENT ( KUBECTL ):
```
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/
```

### Displaying Cluster Information:
```
$ kubectl cluster-info
Kubernetes master is running at https://192.168.99.100:8443
KubeDNS is running at https://192.168.99.100:8443/api/v1/proxy/...
kubernetes-dashboard is running at https://192.168.99.100:8443/api/v1/...
```