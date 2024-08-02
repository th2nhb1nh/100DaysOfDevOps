# Day 9: Introduction to Kubernetes (K8s) Architecture and Components

## Objectives
- Understand the core architecture of Kubernetes.
- Learn about key Kubernetes components and their roles.
- Gain a foundational knowledge of Kubernetes concepts.

## Topics Covered
1. Kubernetes Architecture
2. Kubernetes Components
3. Basic Kubernetes Concepts

## Learning Plan (1-2 Hours)

### Kubernetes Architecture
1. **Overview of Kubernetes Architecture** (20 minutes)
    - Study the high-level architecture of Kubernetes.
    - Understand the control plane and worker nodes.
    - **Notes:**
        - 

### Kubernetes Components
2. **Control Plane Components** (20 minutes)
    - Learn about the components of the control plane: `kube-apiserver`, `etcd`, `kube-scheduler`, `kube-controller-manager`.
    - **Notes:**
        - 
3. **Node Components** (20 minutes)
    - Study the components that run on nodes: `kubelet`, `kube-proxy`, container runtime.
    - **Notes:**
        - 

### Basic Kubernetes Concepts
4. **Pods and Deployments** (20 minutes)
    - Understand the concept of Pods as the basic unit of deployment.
    - Learn about Deployments for managing stateless applications.
    - **Notes:**
        - 
5. **Services and Networking** (20 minutes)
    - Learn about Services for exposing applications.
    - Understand basic networking in Kubernetes.
    - **Notes:**
        - 

### Review and Reflect (10 minutes)
- Summarize what you've learned about Kubernetes architecture and components.
- Reflect on any challenges faced during the learning process and how to overcome them.
- Plan for the next day’s topic: Setting up a local Kubernetes cluster using Minikube or K3s.

## Hands-On Exercises (1 Hour)

### Exercise 1: Exploring Kubernetes Architecture (20 minutes)
- Read documentation and watch videos on Kubernetes architecture.
- Summarize the key components and their roles.

### Exercise 2: Setting Up a Local Environment (20 minutes)
- Install Minikube or K3s on your local machine.
    ```sh
    # Minikube installation example for Linux
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    sudo install minikube-linux-amd64 /usr/local/bin/minikube
    minikube start
    ```
    ```sh
    # K3s installation example for Linux
    curl -sfL https://get.k3s.io | sh -
    sudo k3s kubectl get node
    ```

### Exercise 3: Basic Kubernetes Commands (20 minutes)
- Practice basic `kubectl` commands to interact with your cluster.
    ```sh
    kubectl get nodes
    kubectl get pods --all-namespaces
    kubectl create deployment nginx --image=nginx
    kubectl expose deployment nginx --port=80 --type=NodePort
    ```

## Notes
- 
