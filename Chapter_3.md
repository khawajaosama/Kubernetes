# Chapter # 3:
![](pictures/chap3_logo.jpg)

## Creating Pods from YAML or JSON Descriptors:
You’ll use the kubectl get
command with the -o yaml option to get the whole YAML definition of the pod, as
shown in the following listing.
```
$ kubectl get po kubia-zxzij -o yaml
```
![](pictures/chap3.png)

## Creating a Simple YAML Descriptor For a Pod:
A basic pod manifest: kubia-manual.yaml.
```
apiVersion: v1
kind: Pod
metadata:
name: kubia-manual
spec:
containers:
- image: luksa/kubia
name: kubia
ports:
- containerPort: 8080
protocol: TCP
```
create a file and fill with this material
```
$ kubectl create -f kubia-manual.yaml
pod "kubia-manual" created
```
### Helpful Command:
For example, when creating a pod manifest from scratch, you can start by asking
kubectl to explain pods:
```
$ kubectl explain pods
DESCRIPTION:
Pod is a collection of containers that can run on a host. This resource
is created by clients and scheduled onto hosts.
FIELDS:
kind
<string>
Kind is a string value representing the REST resource this object
represents...
metadata <Object>
Standard object's metadata...
spec
<Object>
Specification of the desired behavior of the pod...
status
<Object>
Most recently observed status of the pod. This data may not be up to
date...
```
Kubectl prints out the explanation of the object and lists the attributes the object
can contain. You can then drill deeper to find out more about each attribute. For
example, you can examine the spec attribute like this:
```
$ kubectl explain pod.spec
RESOURCE: spec <Object>
DESCRIPTION:
Specification of the desired behavior of the pod...
podSpec is a description of a pod.
FIELDS:
hostPID
<boolean>
Use the host's pid namespace. Optional: Default to false.
...
volumes
```
### RETRIEVING THE WHOLE DEFINITION OF A RUNNING POD:
After creating the pod, you can ask Kubernetes for the full YAML of the pod or JSON.
```
$ kubectl get po kubia-manual -o yaml
            OR
$ kubectl get po kubia-manual -o json
```
## EDIT the Replication Controller:
```
kubectl edit rc kubia   (opens a VIM Editor) 
```

## Viewing application logs:
```
$ docker logs <container id>
```
### RETRIEVING A POD’S LOG WITH KUBECTL LOGS:
```
$ kubectl logs kubia-manual
Kubia server starting...
```
### SPECIFYING THE CONTAINER NAME WHEN GETTING LOGS OF A MULTI - CONTAINER POD:
If your pod includes multiple containers, you have to explicitly specify the container
name by including the -c <container name> option when running kubectl logs .
```
$ kubectl logs kubia-manual -c kubia
Kubia server starting...
```
### FORWARDING A LOCAL NETWORK PORT TO A PORT IN THE POD:
```
$ kubectl port-forward kubia-8q4q9 70:8080
... Forwarding from 127.0.0.1:70 -> 8080
... Forwarding from [::1]:70 -> 8080
```
```
curl localhost:70
You've hit kubia-8q4q9
```
![](pictures/port.png)

## Organizing pods with labels:
As the number of
pods increases, the need for categorizing them into subsets becomes more and
more evident.For example, with microservices architectures, the number of deployed microser-
vices can easily exceed 20 or more.multiple versions or
releases (stable, beta, canary, and so on) will run concurrently. This can lead to hun-
dreds of pods in the system. Without a mechanism for organizing them, you end up
with a big, incomprehensible mess, such as the one shown in figure. It’s evident you need a way of organizing them into smaller groups based on arbitrary
criteria, so every developer and system administrator dealing with your system can eas-
ily see which pod is which.

![](pictures/multiple_pods.png)

## Introducing labels: