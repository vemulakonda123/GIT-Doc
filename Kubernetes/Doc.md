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



#Some More Commands
Certainly! Here's a list of common Kubernetes (k8s) commands that you might find useful for managing and interacting with Kubernetes clusters:

1. **kubectl get**: Retrieve information about resources.

    - `kubectl get pods`: List all pods in the current namespace.
    - `kubectl get nodes`: List all nodes in the cluster.
    - `kubectl get services`: List all services in the current namespace.
    - `kubectl get deployments`: List all deployments in the current namespace.
    - `kubectl get namespaces`: List all namespaces in the cluster.

2. **kubectl describe**: Show detailed information about a resource.

    - `kubectl describe pod <pod_name>`: Describe details about a specific pod.
    - `kubectl describe node <node_name>`: Describe details about a specific node.
    - `kubectl describe service <service_name>`: Describe details about a specific service.

3. **kubectl create**: Create a resource from a file or inline configuration.

    - `kubectl create -f <filename.yaml>`: Create a resource defined in a YAML file.
    - `kubectl create deployment <deployment_name> --image=<image_name>`: Create a deployment with the specified image.
    - `kubectl create service <service_name> --tcp=<port>:<targetPort>`: Create a service exposing a pod port.

4. **kubectl delete**: Delete a resource.

    - `kubectl delete pod <pod_name>`: Delete a specific pod.
    - `kubectl delete deployment <deployment_name>`: Delete a specific deployment.
    - `kubectl delete service <service_name>`: Delete a specific service.

5. **kubectl apply**: Apply changes to resources defined in a file.

    - `kubectl apply -f <filename.yaml>`: Apply changes to resources defined in a YAML file.

6. **kubectl exec**: Execute a command in a running container.

    - `kubectl exec -it <pod_name> -- <command>`: Execute a command in the specified pod interactively.

7. **kubectl logs**: Retrieve logs from a container.

    - `kubectl logs <pod_name>`: Display logs from the specified pod.

8. **kubectl port-forward**: Forward one or more local ports to a pod.

    - `kubectl port-forward <pod_name> <local_port>:<pod_port>`: Forward a local port to a pod port.

9. **kubectl scale**: Scale a deployment.

    - `kubectl scale deployment <deployment_name> --replicas=<replica_count>`: Scale the specified deployment to the desired number of replicas.

10. **kubectl rollout**: Perform rollouts and rollbacks of deployments.

    - `kubectl rollout status deployment <deployment_name>`: Check the status of a deployment rollout.
    - `kubectl rollout history deployment <deployment_name>`: View the history of a deployment rollout.

These are some of the most commonly used kubectl commands, but Kubernetes offers a vast array of functionalities, so you might need to explore further based on your specific requirements.


#Some More Commands
Sure, here are some more Kubernetes (k8s) commands for various tasks:

11. **kubectl edit**: Edit a resource directly.

    - `kubectl edit pod <pod_name>`: Edit the configuration of a specific pod in your default editor.

12. **kubectl rollout**: Perform rollouts and rollbacks of deployments.

    - `kubectl rollout status deployment <deployment_name>`: Check the status of a deployment rollout.
    - `kubectl rollout history deployment <deployment_name>`: View the history of a deployment rollout.
    - `kubectl rollout undo deployment <deployment_name>`: Rollback a deployment to a previous revision.

13. **kubectl label**: Add or update labels on resources.

    - `kubectl label pod <pod_name> <key>=<value>`: Add a label to a pod.
    - `kubectl label pod <pod_name> <key>-`: Remove a label from a pod.

14. **kubectl annotate**: Add or update annotations on resources.

    - `kubectl annotate pod <pod_name> <key>=<value>`: Add an annotation to a pod.
    - `kubectl annotate pod <pod_name> <key>-`: Remove an annotation from a pod.

15. **kubectl exec**: Execute a command in a running container.

    - `kubectl exec -it <pod_name> -- <command>`: Execute a command in the specified pod interactively.
    - `kubectl exec <pod_name> -- <command>`: Execute a command in the specified pod non-interactively.

16. **kubectl create secret**: Create a secret.

    - `kubectl create secret generic <secret_name> --from-literal=<key>=<value>`: Create a generic secret from literals.
    - `kubectl create secret docker-registry <secret_name> --docker-username=<username> --docker-password=<password> --docker-email=<email>`: Create a secret for Docker registry authentication.

17. **kubectl create/configure**: Commands related to creating and configuring resources.

    - `kubectl create namespace <namespace_name>`: Create a new namespace.
    - `kubectl create role <role_name> --verb=<verb> --resource=<resource>`: Create a role.
    - `kubectl create rolebinding <rolebinding_name> --role=<role_name> --user=<user>`: Create a role binding.

18. **kubectl apply**: Apply changes to resources defined in a file.

    - `kubectl apply -f <filename.yaml>`: Apply changes to resources defined in a YAML file.
    - `kubectl apply -f <directory>`: Apply changes to resources defined in all YAML files in a directory.

19. **kubectl rollout**: Perform rollouts and rollbacks of deployments.

    - `kubectl rollout status deployment <deployment_name>`: Check the status of a deployment rollout.
    - `kubectl rollout history deployment <deployment_name>`: View the history of a deployment rollout.
    - `kubectl rollout undo deployment <deployment_name>`: Rollback a deployment to a previous revision.

20. **kubectl get events**: Retrieve events from the cluster.

    - `kubectl get events`: Display events from all namespaces.
    - `kubectl get events -n <namespace>`: Display events from a specific namespace.

These commands cover a range of tasks involved in managing Kubernetes clusters and resources. 
Depending on your specific use case, you may need to explore additional commands and options.

