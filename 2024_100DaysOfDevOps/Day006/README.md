# Day 6: Introduction to Docker Swarm and Basic Orchestration

- [Day 6: Introduction to Docker Swarm and Basic Orchestration](#day-6-introduction-to-docker-swarm-and-basic-orchestration)
  - [Objectives](#objectives)
  - [Topics Covered](#topics-covered)
  - [Learning Plan (1-2 Hours)](#learning-plan-1-2-hours)
    - [Docker Swarm Overview](#docker-swarm-overview)
    - [Setting Up a Docker Swarm Cluster](#setting-up-a-docker-swarm-cluster)
    - [Docker Swarm Nodes and Services](#docker-swarm-nodes-and-services)
    - [Basic Docker Swarm Commands](#basic-docker-swarm-commands)

## Objectives
- Understand Docker Swarm and its architecture.
- Learn to set up and manage a Docker Swarm cluster.
- Deploy services and applications on Docker Swarm.

## Topics Covered
1. Docker Swarm Overview
2. Setting Up a Docker Swarm Cluster
3. Docker Swarm Nodes and Services
4. Basic Docker Swarm Commands

## Learning Plan (1-2 Hours)

### Docker Swarm Overview
1. **Introduction to Docker Swarm** (15 minutes)
    - Understand what Docker Swarm is and its benefits for orchestration.
    - **Notes:**
      - a docker's native clustering and orchestration (similar to k8s)
      - pros:
        - **native tool with docker:a** easy to use with docker cli + api; can use the same `docker-compose.yaml` file to deploy not only one but multiple node setup.
        - **ha (high availability):** fault tolerance (auto-create new node when other fail to make sure application works fine); 

### Setting Up a Docker Swarm Cluster
2. **Initialize a Swarm** (20 minutes)
    - Initialize a Docker Swarm on a manager node.
        ```sh
        docker swarm init
        ```
    - Add worker nodes to the Swarm.
        ```sh
        docker swarm join --token <token> <manager-ip>:2377
        ```
    - **Notes:**
        - 

### Docker Swarm Nodes and Services
3. **Managing Nodes and Services** (20 minutes)
    - List and inspect Swarm nodes.
        ```sh
        docker node ls
        docker node inspect <node-id>
        ```
    - Create and manage services.
        ```sh
        docker service create --name my-service -p 80:80 nginx
        docker service ls
        docker service ps my-service
        ```
    - **Notes:**
        - 

### Basic Docker Swarm Commands
4. **Using Docker Swarm Commands** (15 minutes)
    - Learn essential commands to manage Docker Swarm clusters and services.
        ```sh
        docker swarm update
        docker service scale my-service=3
        docker service update --image nginx:latest my-service
        docker service rm my-service
        ```
    - **Notes:**
        - 
