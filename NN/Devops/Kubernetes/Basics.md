Kubernetes, often abbreviated as K8s, is an open-source platform designed to automate the deployment, scaling, and management of containerized applications. Developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF), Kubernetes helps in orchestrating containers across a cluster of machines, making it easier to manage complex applications at scale.



Kubernetes architecture 
Kubernetes cluster consistent from:
- One master node (master node or control plane)
- Many worker nodes (physical or virtual machines) where each node has **kubelet process run on it**. each worker node has different container run on it

##### Kubelet ()
is a Kubernetes process that makes it possible for the cluster to talk to each other and actually execute some tasks on these node


In Kubernetes, the **control plane** and **worker nodes** are two fundamental components that work together to manage and run containerized applications.

### 1. **Control Plane**

Master is running several Kubernetes processes that are absolutely necessary to run and manage the cluster properly.

The control plane is the brain of the Kubernetes cluster. It manages the overall state of the cluster, including scheduling, scaling, and maintaining the desired state of applications. The control plane consists of several components:

- **API Server (`kube-apiserver`)**: Is container an API server is the entry point to the Kubernetes cluster so Acts as the frontend of the control plane. It exposes the Kubernetes API, which is used by all components within the cluster to interact with the control plane. The API server processes REST requests from users, other control plane components, and worker nodes.

- **Controller Manager (`kube-controller-manager`)**: is another container (process) keep an overview what's happing in the cluster whether something need to be repaired or maybe if a container died and it needs to be restarted etc.

- **ETCD**: A distributed key-value store that stores all cluster data, including the configuration data inside , current state of each node and each container inside of that node and backup  and restore using ETCD SNAPSHOT metadata, and more. It serves as the primary data store for Kubernetes.
    
- **Scheduler (`kube-scheduler`)**: Decides on which worker node a newly created Pod should run, based on resource requirements, policy constraints, and other factors.
    
- **Cloud Controller Manager** (if the cluster is running on a cloud provider): Manages integration with the cloud provider’s infrastructure, such as load balancers, volumes, and networking.
    

The control plane components typically run on a dedicated set of nodes (often called master nodes) within the cluster to ensure stability and high availability.

### 2. **Worker Nodes**

Worker nodes are the machines (physical or virtual) that actually run the containerized applications. Each worker node contains the following key components:

- **Kubelet**: An agent running on each worker node that ensures containers are running in a Pod. It communicates with the control plane through the API server, receives tasks (like launching or stopping containers), and reports back on the node's health and status.
    
- **Kube-proxy**: A network proxy that maintains network rules on nodes. It allows for communication between different Pods and services within and outside the cluster.
    
- **Container Runtime**: The software responsible for running containers. While Kubernetes supports several runtimes (like Docker, containerd, and CRI-O), the runtime is the component that actually pulls container images and executes them.
    

#### **Why Worker Nodes Have More Resources Than Master Nodes**

because they are running the applications on inside of it usually are much bigger and have more resources because they will be running hundreds of containers inside of them whereas master

#### Why Backup the Master Node

master node is much more important than the individual worker nodes because if for example you lose a master node access you will not be able to access the cluster anymore and that means that you absolutely have to have a backup of your Kubernetes cluster but in more cases of course you're going to have multiple musters where if one muster node s down the cluster continues to function smoothly because you have other masters available



### Key Features of Kubernetes:

1. **Automated Rollouts and Rollbacks**: Kubernetes can automatically roll out changes to applications or configurations, including rolling back to previous versions if something goes wrong.
    
2. **Load Balancing and Service Discovery**: Kubernetes can automatically distribute traffic across multiple containers, making it easy to balance load and ensure high availability.
    
3. **Self-Healing**: If a container fails, Kubernetes automatically restarts it, replaces it, or reschedules it to ensure continuous operation.
    
4. **Storage Orchestration**: It can automatically mount storage systems like local storage, public cloud providers, and network storage.
    
5. **Secret and Configuration Management**: Kubernetes allows you to securely store and manage sensitive information, such as passwords, OAuth tokens, and SSH keys.
    
6. **Scaling**: Kubernetes can scale applications up or down automatically based on resource utilization, allowing applications to handle varying loads efficiently.
    

### Core Components:

- **Pods**: The smallest unit in Kubernetes, representing one or more containers that share the same network namespace and storage.
- **Nodes**: Physical or virtual machines that run your containers.
- **Clusters**: A set of nodes managed by Kubernetes.
- **Services**: Abstracts the logic of containers and exposes them to the outside world or other internal components.
- **Namespaces**: Provides a way to divide cluster resources between multiple users.

Kubernetes is highly flexible and can work with various container runtimes, cloud providers, and storage systems, making it a preferred choice for deploying modern, distributed applications.