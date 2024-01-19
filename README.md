# Kaiburr Task 2 : API Deployment with Kubernetes on Minikube

This repository contains the Kubernetes manifests and Dockerfiles for deploying the Spring Boot API application connected to MongoDB (created in Task 1) on a Minikube cluster.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)



## 1. Build and Push Docker Image

```bash
docker build . -t arunodhai/kaiburrapi
docker push arunodhai/kaiburrapi
```

## 2. Start Minikube Cluster

```bash
minikube start
```

## Deploy springboot API and MongoDB
```bash
kubectl create -f mongo-pvc.yml
kubectl create -f mongo-deployment.yml
kubectl create -f mongo-service.yml
kubectl create -f deployment.yml
kubectl create -f service.yml
```


