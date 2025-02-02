# Kubernetes-Blog-Series

![Last Commit](https://img.shields.io/github/last-commit/AimeeKnight/Kubernetes-Blog-Series)
![Contributors](https://img.shields.io/github/contributors/AimeeKnight/Kubernetes-Blog-Series)
![Commit Count](https://img.shields.io/github/commit-activity/y/AimeeKnight/Kubernetes-Blog-Series)
[![Documentation](https://img.shields.io/badge/docs-website-blue.svg)](https://AimeeKnight.github.io/Kubernetes-Blog-Series/)

## Summary

This repository is dedicated to the development of a blog series focused on Kubernetes and modern infrastructure. It covers various topics, including the transition from traditional deployments to cloud-native architecture, microservices, immutable infrastructure, and more.
![Kubernetes Logo](https://raw.githubusercontent.com/kubernetes/kubernetes/master/logo/logo.png)
![CNCF Badge](https://img.shields.io/badge/CNCF-Kubernetes-blue)

## Table of Contents

- [Intro](#intro)
  1. [From HTTP to API](#from-http-to-api)
  2. [Monolith to Microservice](#monolith-to-microservice)
  3. [Cattle not Pets](#cattle-not-pets)
  4. [Infrastructure as Code](#infrastructure-as-code)
  5. [Continuous Integration (CI)](#continuous-integration-ci)
- [Understanding K8s](#understanding-k8s)
  1. [Containers 101](#containers-101)
  2. [Kubernetes Architecture](#kubernetes-architecture)
- [Using K8s in the Real World](#using-k8s-in-the-real-world)
  1. [Scaling with HPAs](#scaling-with-hpas)
- [Reference](#reference)
  1. [Lexicon](#lexicon)

## Intro

1. [**From HTTP to API**](content/intro/http_2_api.md)
   - Understand the transition from traditional HTTP-based services to modern API-driven architectures.
   - Learn about REST, gRPC, and GraphQL APIs.

2. [**Monolith to Microservice**](content/intro/vms_to_containers.md)
   - Explore the migration from monolithic applications to microservices.
   - Understand the benefits of microservices, such as scalability, resilience, and maintainability.
   - Learn about strategies for breaking down monolithic applications into microservices.

3. [**Cattle not Pets**](content/intro/dividing_with_microservices.md)
   - Embrace the concept of treating servers as disposable resources (cattle) rather than unique entities (pets).
   - Understand the benefits of immutable infrastructure and automated deployments.

4. [**Infrastructure as Code**](content/intro/immutable_infra.md)
   - Explore tools like Terraform, Ansible, and Kubernetes for defining and managing infrastructure.
   - Understand the principles of version control, repeatability, and scalability in infrastructure management.
   - Learn about managing infrastructure using code and automation tools.

5. [**Continuous Integration (CI)**](content/intro/continuous_integration.md)
   - Learn about CI practices and tools to automate testing and deployment.

## Understanding K8s

1. [**Containers 101**](content/understanding_k8s/containers_101.md)
   - Introduction to container technology, its benefits, and how it differs from traditional virtualization.
   - Learn about Docker, container lifecycle, and basic commands.

2. [**Kubernetes Architecture**](content/understanding_k8s/kubernetes_arch.md)
   - Detailed overview of Kubernetes architecture and its components.
   - Understand the roles of the master node, worker nodes, and key concepts like pods, services, and deployments.

## Using K8s in the Real World

1. [**Scaling with HPAs**](content/using_k8s/scaling_with_hpas.md)
   - Learn about Horizontal Pod Autoscalers (HPAs) and how they help in scaling applications dynamically.

## Reference

1. [**Lexicon**](content/reference/K8s_Lexicon.md)
   - A glossary of terms and concepts related to Kubernetes and cloud-native infrastructure.

## Continuous Integration (CI)

This repository uses GitHub Actions for Continuous Integration (CI) to ensure code quality and consistency. The CI pipeline includes the following checks:

1. **Markdown Linting**
   - Uses `markdownlint-cli` to lint all Markdown files in the repository.
   - Ensures that Markdown files adhere to a consistent style and format.

2. **Spell Checking**
   - Uses `cspell` to check for spelling errors in Markdown files.
   - Helps maintain the quality and readability of documentation.

3. **Link Checking**
   - Uses `markdown-link-check` to verify that all links in Markdown files are valid.
   - Ensures that documentation does not contain broken links.

The CI configuration can be found in the `.github/workflows/Doc-ci.yaml` file.
