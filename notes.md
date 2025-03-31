# KUBERNETES COURSE NOTES

### Cluster Architecture

1. Master Node(s) (Control Plane)
2. Worker Nodes (Node/Minions)

1. Master Node:
⋅⋅* kube-apiserver (API SERVER):
⋅⋅⋅ ⋅⋅* Central Component of the control plane. 
⋅⋅⋅ ⋅⋅* Exposes the Kubernetes API and serves as the entry point for all interactions with the cluster. 
⋅⋅⋅ ⋅⋅* Processes REST requests from users, the kubernetes dashboard and other componenets in the system. 

⋅⋅* kube-scheduler (SCHEDULER):
⋅⋅⋅ ⋅⋅* The scheduler watches for newly created pods that have no assigned node and assigns them to an appropriate worker node based on available resources, constraints and policies.

⋅⋅* kube-controller-manager (Controller Manager):




