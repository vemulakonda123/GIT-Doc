##Kubernetes starts with four initial namespaces:

default
Kubernetes includes this namespace so that you can start using your new cluster without first creating a namespace.
kube-node-lease
This namespace holds Lease objects associated with each node. Node leases allow the kubelet to send heartbeats so that the control plane can detect node failure.
kube-public
This namespace is readable by all clients (including those not authenticated). This namespace is mostly reserved for cluster usage, in case that some resources should be visible and readable publicly throughout the whole cluster. The public aspect of this namespace is only a convention, not a requirement.
kube-system
The namespace for objects created by the Kubernetes system.



##Viewing namespaces
You can list the current namespaces in a cluster using:

```
kubectl get namespace
```
```
NAME              STATUS   AGE
default           Active   1d
kube-node-lease   Active   1d
kube-public       Active   1d
kube-system       Active   1d
```

##Setting the namespace for a request
Example
```
kubectl run nginx --image=nginx --namespace=<insert-namespace-name-here>
kubectl get pods --namespace=<insert-namespace-name-here>
```
##Setting the namespace preference
###You can permanently save the namespace for all subsequent kubectl commands in that context.
```
kubectl config set-context --current --namespace=<insert-namespace-name-here>
# Validate it
kubectl config view --minify | grep namespace:
```


###To see which Kubernetes resources are and aren't in a namespace:
```
# In a namespace
kubectl api-resources --namespaced=true

# Not in a namespace
kubectl api-resources --namespaced=false
```