# Kubernetes Node Demo

This is a basic Node.js Express application deployed using Docker and Kubernetes. The goal of this project was to practice building, containerizing, and deploying an application into a local Kubernetes cluster using Minikube on WSL2 — no cloud resources involved.

## Features

- Minimal Node.js server (`server.js`)
- Containerized with a lightweight Dockerfile
- Deployment managed via Kubernetes `Deployment` and `Service` manifests
- Exposed locally through a NodePort Service

## Purpose

To get hands-on with core Kubernetes concepts such as:

- Pods, ReplicaSets, and Deployments
- Services
- Local container builds using Minikube’s Docker engine
- Using `kubectl` to interact with and troubleshoot your cluster

## Running locally

**Prerequisites**

- WSL2 and Ubuntu
- Docker
- kubectl
- Minikube

**Steps**

```bash
eval $(minikube docker-env)
docker build -t node-k8s-demo:latest .
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
minikube service node-demo-service
