Minikube is a tool that sets up a Kubernetes environment on a local PC or laptop but with only single node acts as control plane (master node) and as worker node in same time. It’s technically a Kubernetes distribution

```
minikube start
```

get the minikube cluster status tells you if the cluster running and configured

```
minikube status
```


## kubectl

display all pods in the cluster
```
kubectl get pods
```

display all nodes in the cluster
```
kubectl get nodes
```


access the dashboard of Kubernetes

```
kubectl dashboard
```



###### Config file

contains information 

To view cluster config file

```
kubectl config view
```


The command `kubectl config current-context` is used to display the currently active context in the Kubernetes configuration file (`kubeconfig`). A context in Kubernetes represents a specific cluster, namespace, and user combination that `kubectl` will interact with by default.

```
kubectl config current-context
```

- **`kubectl`**: The command-line tool for interacting with a Kubernetes cluster.
- **`config`**: Subcommand to modify or read configuration options.
- **`current-context`**: The specific operation to retrieve the current context.

When you run this command, it reads the configuration file (usually found in `~/.kube/config`) and prints the name of the context that is currently in use. This context dictates which cluster `kubectl` will communicate with unless a different context is specified in a command.



he `kubectl get all` command retrieves information about all the common Kubernetes resources in the current namespace. This includes:

```
kubectl get all
```