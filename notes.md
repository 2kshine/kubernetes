# KUBERNETES COURSE NOTES

### Cluster Architecture
> Architecture can be divided into two main parts
>> Master Node(s) (Control Plane) and Worker Nodes (Node/Minions)

1. **Master Node:**
    1. kube-apiserver (API SERVER):
        - Central Component of the control plane. 
        - Exposes the Kubernetes API and serves as the entry point for all interactions with the cluster. 
        - Processes REST requests from users, the kubernetes dashboard and other componenets in the system. 

    2. kube-scheduler (SCHEDULER):
        - The scheduler watches for newly created pods that have no assigned node and assigns them to an appropriate worker node based on available resources, constraints and policies.

    3. kube-controller-manager (Controller Manager):
        - Runs controllers that ensure the desired state of the system is maintained. Responsible for checking and correcting any changes in the clusters.
        - eg, deployment controller, ReplicaSet Controller and Node controller.
    
    4. etcd:
        - Distributed key-value store used by kubernetes to store all cluster data. 
        - Stores cluster's state, including information about nodes pods, services and configs.

2. **Worker Nodes:**
    1. kubelet:
        - An agent that runs on each worker node to ensure that the containers are running in a POD and reports the status of the node and containers back to the api server.
        - monitors the node's health and makes sure that containers are started, running and terminated as needed. 
    2. kube-proxy:
        - Maintains network rules on the worker nodes and ensures that network traffic is routed to the correct container. allows communication between services across nodes. 
        - can be configured to use iptables or IPVS for load balancing network traffic between pods.
    3. Container Runtime:
        - Software responsible for running containers on each worker node. eg, Docker, containerd, and CRI-O
    4. Pods:
        - Smallest and simplest unit in Kubernetes. Contain one or more containers and share storage, network and specs for how to run the containers.
        - Each pod runs on a worker node and communicates with other pods and services in the cluster.