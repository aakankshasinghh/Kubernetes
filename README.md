# Kubernetes
an open-source system for automating the deployment, scaling, and management of containerized applications

Architecture of Kubernetes
 1. Data Plane (Worker)
 2. Control Plane (Master)

    Data Plane- Run the actual applications (containers) and provide resources like CPU, memory, and storage.
    Components-
    1. Kubelet
    2. Kube-Proxy
    3. Container Runtime

    Control Plane- Responsible for managing the cluster, making global decisions, and maintaining desired state.
    Components-
    1. API Server
    2. Scheduler
    3. Controller Manager
    4. Cloud Controller Manager
    5. etcd
   

# Control Plane Components

These run on the master node(s) and manage the cluster:

API Server- The entry point to Kubernetes, Exposes REST APIs to interact with the cluster, All communication (kubectl, dashboard, other components) goes through it.

etcd- A distributed key-value store, Stores all cluster data (configuration, state, secrets, etc.), Acts as the "source of truth" for the cluster.

Scheduler- Assigns workloads (Pods) to nodes, considers resource availability, constraints, and affinity rules.

Controller Manager- Runs controllers that watch the cluster state and reconcile it to the desired state. Examples: Node Controller, Replication Controller, Endpoints Controller.

Cloud Controller Manager- Integrates with the underlying cloud provider for services like load balancers, storage, and networking.

# Worker Node Components

Each worker node runs services required to host and manage application pods:

Kubelet- An agent that runs on each node. Ensures containers are running as expected. Talks to the API server.

Kube-Proxy- Manages networking and load balancing for services. Handles communication between pods and external clients.

Container Runtime- Software to run containers (Docker, containerd, CRI-O, etc.).

Pulls images and starts/stops containers.
       
