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
<img width="1440" alt="Docker image build and push" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/a889879e-e19d-496e-b5c5-f8aea8e4463f">

### Testing the Docker Image by running it
<img width="1440" alt="Running docker image" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/d3c34ad2-f512-4a54-8cde-38d3a8371b16">

## 2. Start Minikube Cluster

```bash
minikube start
```
<img width="1440" alt="minikube setup" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/87cd9e3e-0ab2-49c0-9be0-deaf1beeebdb">

## 3. Deploy springboot API and MongoDB
```bash
kubectl create -f mongo-pvc.yml
kubectl create -f mongo-deployment.yml
kubectl create -f mongo-service.yml
kubectl create -f deployment.yml
kubectl create -f service.yml
```
<img width="1440" alt="deployments and services creations" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/30c27d17-f8f9-43d2-ad3b-d0dbfab80df9">

## 4. Verify Deployment
```bash
kubectl get all
```
<img width="1440" alt="Status" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/af15af71-b11b-45bb-928a-bb758b70ff6c">
