# Day 5: Refresh Docker Fundamentals and Multi-Container Applications with Docker Compose

- [Day 5: Refresh Docker Fundamentals and Multi-Container Applications with Docker Compose](#day-5-refresh-docker-fundamentals-and-multi-container-applications-with-docker-compose)
  - [Objectives](#objectives)
  - [Topics Covered](#topics-covered)
  - [Learning Plan (1-2 Hours)](#learning-plan-1-2-hours)
    - [Docker Images and Containers](#docker-images-and-containers)
    - [Docker Networking and Volumes](#docker-networking-and-volumes)
    - [Introduction to Docker Compose](#introduction-to-docker-compose)
    - [Writing Docker Compose Files](#writing-docker-compose-files)
    - [Managing Multi-Container Applications with Docker Compose](#managing-multi-container-applications-with-docker-compose)

## Objectives
- Refresh Docker fundamentals and core concepts.
- Learn to manage multi-container applications using Docker Compose.
- Practice creating and deploying a multi-container application.

## Topics Covered
1. Docker Images and Containers
2. Docker Networking and Volumes
3. Introduction to Docker Compose
4. Writing Docker Compose Files
5. Managing Multi-Container Applications with Docker Compose

## Learning Plan (1-2 Hours)

### Docker Images and Containers
2. **Working with Docker Images and Containers** (20 minutes)
    - Review commands to build, run, and manage Docker images and containers.
        ```sh
        docker images                   # show local images
        docker build -t my-image .      # build container from Dockerfile in the current dir
        docker run -d --name my-container my-image      # run container in detached mode
        docker pull my-image            # pull image from container registry
        docker ps                       # list all running containers
        docker exec -it my-container /bin/bash          # execute command in container
        docker stop my-container        # stop my-container 
        docker rm my-container          # remove my-container
        docker rmi my-image             # remove image my-image
        ```

### Docker Networking and Volumes
3. **Networking and Volumes** (20 minutes)
    - Review Docker networking concepts and volume management.
        ```sh
        docker network create my-network
        docker volume create my-volume
        docker run -d --name my-container --network my-network -v my-volume:/data my-image
        ```
    - **Notes:**
        - Docker networking allows containers to communicate with each other and the internet. The default option is bridge.
        - Docker volume is used to persist data generated or used by containers, this could be shared among containers.

### Introduction to Docker Compose
4. **Docker Compose Overview** (10 minutes)
    - Learn the basics of Docker Compose and its benefits for managing multi-container applications.
    - **Notes:**
        - Docker compose is used for **multi-container** management. It uses `.yaml` file to define and manage services, networks, volumes for your apps. One benefit is scalable.

### Writing Docker Compose Files
5. **Creating a Docker Compose File** (15 minutes)
    - Write a `docker-compose.yml` file to define a multi-container application.
        ```yaml
        version: '3'
        services:
          web:
            image: nginx
            ports:
              - "80:80"
          db:
            image: mysql
            environment:
              MYSQL_ROOT_PASSWORD: example
        ```

### Managing Multi-Container Applications with Docker Compose
6. **Using Docker Compose Commands** (20 minutes)
    - Learn commands to manage multi-container applications.
        ```sh
        docker-compose up -d
        docker-compose ps
        docker-compose logs                                 # show logs of all services
        docker-compose up --scale <service_name>=<number_of_instances>      # scale the specific service to the desired number of instances
        docker-compose stop
        docker-compose down
        docker-compose exec <service_name> <command>        # run command inside container managed by docker compose
        ```
    - **Notes:**
        - You can define `healthcheck` to ensure instances running correctly
        ```yaml
        version: '3.8'

        services:
        web:
            image: nginx:latest
            depends_on:
            - db
            healthcheck:
            test: ["CMD", "curl", "-f", "http://localhost"]
            interval: 30s
            timeout: 10s
            retries: 5

        db:
            image: postgres:latest
            environment:
            POSTGRES_DB: exampledb
            POSTGRES_USER: exampleuser
            POSTGRES_PASSWORD: examplepass
            volumes:
            - db_data:/var/lib/postgresql/data

        volumes:
        db_data:
        ```
