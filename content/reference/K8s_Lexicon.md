# Kubernetes Lexicon

Welcome to the Kubernetes Lexicon! This reference page will help you understand key terms and concepts used in our Kubernetes blog series.

## Table of Contents
1. [Pod](#pod)
2. [Node](#node)
3. [Cluster](#cluster)
4. [Namespace](#namespace)
5. [Deployment](#deployment)
6. [Service](#service)
7. [ConfigMap](#configmap)
8. [Secret](#secret)
9. [PersistentVolume (PV)](#persistentvolume-pv)
10. [PersistentVolumeClaim (PVC)](#persistentvolumeclaim-pvc)

## Pod
A Pod is the smallest and simplest Kubernetes object. It represents a single instance of a running process in your cluster.

## Node
A Node is a worker machine in Kubernetes. It can be a virtual or physical machine, depending on the cluster.

## Cluster
A Cluster is a set of Nodes that run containerized applications managed by Kubernetes.

## Namespace
A Namespace is a way to divide cluster resources between multiple users. It provides a scope for names.

## Deployment
A Deployment provides declarative updates to applications. It describes the desired state and the controller changes the actual state to the desired state.

## Service
A Service is an abstraction that defines a logical set of Pods and a policy by which to access them.

## ConfigMap
A ConfigMap is an API object used to store non-confidential data in key-value pairs. Pods can consume ConfigMaps as environment variables, command-line arguments, or configuration files.

## Secret
A Secret is similar to a ConfigMap but is intended to hold sensitive information, such as passwords, OAuth tokens, and ssh keys.

## PersistentVolume (PV)
A PersistentVolume (PV) is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using Storage Classes.

## PersistentVolumeClaim (PVC)
A PersistentVolumeClaim (PVC) is a request for storage by a user. It is similar to a Pod in that Pods consume node resources, and PVCs consume PV resources.
