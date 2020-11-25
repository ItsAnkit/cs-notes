``Highly available container orchestrator``

#### Pod
    A group of containers that share IP and volume.

``A pod will always run on a node(worker). Think of a node like a worker machine managed by the master. A node can have multiple pods, and the master automatically schedules the pods across a node.``

#### Replication controller
    Replicating pods

#### Services (as in Microservices)
    A service allows Kubernetes to set a single DNS record for a set of pods. 
    Kubernetes gives pods their own IP addresses and a single DNS name for a set of Pods, and can load-balance across them.
    Pods are nonpermanent resources. They can cause problem if some backend pod is changed, so which pod the frontend pod will request to. Service is an abstraction which defines a logical set of Pods and a policy by which to access them  even if pods change.