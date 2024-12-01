# kubernetes-notes
Notes for Kubernetes

# What is kubernetes
- An orchestration/ management platform that manages docker containers.
- It provides a framework for managing complex tasks of deploying and scaling of applications.
- It is written in Go programming languange just like docker thats why they work together smoothly.

## Advantages of Kubernetes
- Orchestrate/ Manage container
- Auto scaling: Basically adding and removing container based on user traffic.
- Self Healing: Meaning that when a container is damage or somehow stop working for some reason kubernetes will replace that damage container will new container.
- Load Balancing

## Kubernetes Architecture
Works based on cluster architecture: Cluster means group of servers.

## Ways to interact to Kubernetes
1. Using the UI (Web Dashboard)
2. Using the CLI

### Control Plane/ Master Node
- In analogy it's like the manager.

1. API Server
- Takes all incoming requests coming from either which you are using the UI based or CLI based and store that in etcd.
2. ETCD
- It is the internal database in kubernetes.
- Written also in Go from the ground up.
- Key value store.
3. Scheduler
- Will check all the pending tasks in etcd and will call the controller manager to execute those pending tasks if there's any.
4. Controller Manager
- Will be the one who will assign the task and talk to worker node (kubelet) to execute the request.

### Workner Node
- In analogy it's like the employees
- Can contain many pods.

## Kubelet/ Node agent
- In analogy it is the personal assistant of worker node.
## Kube proxy
- Will provide the networking of the kubernetes.
## Pod 
- Is nothing but a process inside kubernetes. Which you can create many instances of your applications inside a Pod.
- Smallest building block in kubernetes.
- Represent runtime instance of your applications.

- POD contains an docker image that can spawn up many docker containers from that image.
- Meaning that one POD can have a single docker image and multiple containers from that image.
- But its recommended to run one container inside one POD but you know that its possible to run multiple containers in one POD but its recommended only run one container inside 1 POD so 1 POD, 1 Container.
- For every POD 1 IP Address will be generated
- MANIFEST YML is used to create a POD
- POD cannot be accessed outside the kubernetes cluster meaning that PODs are only available. inside the kubernetes cluster. To access the POD outside the kubernetes cluster you will use kubernetes service concept
## Docker engine
- You know what this is for right

# Kubernetes Setup
‌Self Managed Kubernetes Cluster
Minikube (For single kubernetes cluster)
- For your local machine and for learning and testing purposes
Kubeadm (For multiple kubernetes cluster)
- For deployement
‌Managed Kubernetes Cluster (Cloud Providers)
AWS EKS (Most recommended)
Azure EKS
GCP GKE
IBM IKE
