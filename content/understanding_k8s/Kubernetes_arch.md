# Kubernetes Architecture

## Introduction
Kubernetes is an open-source platform designed to automate deploying, scaling, and operating application containers. This document outlines the basic building blocks of Kubernetes architecture.

## Components

### 1. Master Node
The master node is responsible for managing the Kubernetes cluster. It consists of several key components:
- **API Server**: Exposes the Kubernetes API.
- **etcd**: A consistent and highly-available key-value store used for configuration data.
- **Controller Manager**: Runs controller processes to regulate the state of the cluster.
- **Scheduler**: Assigns workloads to nodes based on resource availability.

```
+---------------------------+
|        Master Node        |
|  +---------------------+  |
|  |      API Server     |  |
|  +---------------------+  |
|  +---------------------+  |
|  |        etcd         |  |
|  +---------------------+  |
|  +---------------------+  |
|  | Controller Manager  |  |
|  +---------------------+  |
|  +---------------------+  |
|  |      Scheduler      |  |
|  +---------------------+  |
+---------------------------+
```

### 2. Worker Nodes
Worker nodes run the containerized applications. Each node contains the following components:
- **Kubelet**: An agent that ensures containers are running in a Pod.
- **Kube-proxy**: Maintains network rules and handles communication within the cluster.
- **Container Runtime**: Software responsible for running containers (e.g., Docker, containerd).


```
+---------------------------+
|        Worker Node        |
|  +---------------------+  |
|  |       Kubelet       |  |
|  +---------------------+  |
|  +---------------------+  |
|  |     Kube-proxy      |  |
|  +---------------------+  |
|  +---------------------+  |
|  |  Container Runtime  |  |
|  +---------------------+  |
+---------------------------+
```

### 3. Pods
Pods are the smallest deployable units in Kubernetes, consisting of one or more containers that share storage and network resources.
```
+---------------------------+
|           Pod             |
|  +---------------------+  |
|  |     Container 1     |  |
|  +---------------------+  |
|  +---------------------+  |
|  |     Container 2     |  |
|  +---------------------+  |
+---------------------------+
```




### 4. Services
Services provide a stable IP address and DNS name to a set of Pods, enabling communication between different parts of the application.
```
+---------------------------+
|          Service          |
|  +---------------------+  |
|  |        Pod 1        |  |
|  +---------------------+  |
|  +---------------------+  |
|  |        Pod 2        |  |
|  +---------------------+  |
+---------------------------+
```

### 6. Deployments
Deployments are used to manage the deployment of applications in a Kubernetes cluster. They ensure that the desired number of replicas of a Pod are running at all times. Deployments provide features such as rolling updates and rollbacks.

```
+---------------------------+
|        Deployment         |
|  +---------------------+  |
|  |       Service       |  |
|  +---------------------+  |
|                           |
|  +---------------------+  |
|  |     Worker Node 1   |  |
|  |  +---------------+  |  |
|  |  |     Pod 1     |  |  |
|  |  |  +---------+  |  |  |
|  |  |  |Container|  |  |  |
|  |  |  +---------+  |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
|                           |
|  +---------------------+  |
|  |     Worker Node 2   |  |
|  |  +---------------+  |  |
|  |  |     Pod 2     |  |  |
|  |  |  +---------+  |  |  |
|  |  |  |Container|  |  |  |
|  |  |  +---------+  |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```

Deployments manage the lifecycle of Pods and ensure that the specified number of replicas are running. They also handle updates to the application by creating new Pods with the updated configuration and gradually replacing the old Pods.

### 7. Ingress
```
#### Need for Ingress
Ingress in Kubernetes is used to manage external access to services within a cluster, typically HTTP and HTTPS traffic. It provides a way to define rules for routing traffic to different services based on the request's host or path. Without ingress, exposing services to the outside world would require creating a separate load balancer for each service or using NodePort, which can be inefficient and harder to manage.

#### Types of Ingress

1. **Ingress**
    - The Ingress resource defines rules for routing HTTP and HTTPS traffic to services within the cluster. It allows for host-based or path-based routing and can also handle SSL termination.
    ```
    +---------------------------+
    |         Ingress           |
    |  +---------------------+  |
    |  |      example.com    |  |
    |  +---------------------+  |
    |  +---------------------+  |
    |  |       /path         |  |
    |  +---------------------+  |
    |           |                 |
    |           v                 |
    |  +---------------------+  |
    |  |   example-service   |  |
    |  +---------------------+  |
    +---------------------------+
    ```

2. **MetalLB**
    - MetalLB is a load-balancer implementation for bare metal Kubernetes clusters, providing a way to expose services externally using standard network load-balancing protocols.
    ```
    +---------------------------+
    |         MetalLB           |
    |  +---------------------+  |
    |  |    External IP     |  |
    |  +---------------------+  |
    |           |                 |
    |           v                 |
    |  +---------------------+  |
    |  |   my-service       |  |
    |  +---------------------+  |
    +---------------------------+
    ```

3. **NodePort**
    - NodePort is a type of service that exposes the service on a static port on each node's IP address. It allows external traffic to access the service using `<NodeIP>:<NodePort>`.
    ```
    +---------------------------+
    |         NodePort          |
    |  +---------------------+  |
    |  |   <NodeIP>:30007    |  |
    |  +---------------------+  |
    |           |                 |
    |           v                 |
    |  +---------------------+  |
    |  | example-service    |  |
    |  +---------------------+  |
    +---------------------------+
    ```

Each of these ingress methods has its own use cases and benefits, and the choice depends on the specific requirements and environment of the Kubernetes deployment.
```


### 5. ConfigMaps and Secrets
- **ConfigMaps**: Store configuration data in key-value pairs.
- **Secrets**: Store sensitive information, such as passwords and tokens, in an encrypted format.

## Conclusion
Understanding the basic building blocks of Kubernetes architecture is essential for managing and deploying applications effectively. This document provides a high-level overview of the key components involved.

