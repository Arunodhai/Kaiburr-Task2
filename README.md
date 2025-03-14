# API Deployment with Kubernetes on Minikube

This repository contains the Kubernetes manifests and Dockerfile for deploying the Spring Boot API application connected to MongoDB (created in Task 1) on a Minikube cluster.

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

## 3. Deploying the manifests

```bash
kubectl create -f mongo-deployment.yml
kubectl create -f mongo-service.yml
kubectl create -f mongo-pvc.yml
kubectl create -f deployment.yml
kubectl create -f service.yml
```
<img width="1440" alt="deployments and services creations" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/30c27d17-f8f9-43d2-ad3b-d0dbfab80df9">

## 4. Verify Deployment

```bash
kubectl get all
```
<img width="1440" alt="Status" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/af15af71-b11b-45bb-928a-bb758b70ff6c">

## 5. Accessing the Kaiburr API Service

```bash
minikube service kaiburr-api-service
```
### Checking the PUT Method
<img width="1440" alt="PUT method" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/c49f3d7d-6b4e-4899-ac85-5642bc8a456b">

### Checking the GET Method
<img width="1440" alt="GET method" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/8c67cadb-a1d7-4bb6-b493-7a8220e57a34">

### Checking in browser
<img width="1440" alt="Browser view GET method" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/b101fa88-1088-4142-9fd4-4ca6ea913306">

### Checking API endpoints using curl
<img width="1440" alt="CURL methods" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/0d52421f-5969-4f6c-b2f7-641cbe3cde08">

## 6. Checking MongoDB Data Inside the Running Pod

```bash
kubectl exec -it mongo-deployment-df7b8b9c-sf8nh -- /bin/bash 
```
### To open the mongo shell inside the MongoDB running Pod
```bash
mongosh
```
<img width="1440" alt="Viewing data inside mongodb pod" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/685af247-2fd6-4a65-8f62-c7ed4295c758">

## 7. Checking Persistent Volume Claim (PVC) by deleting mongoDB pod
### To view PVC
```bash
kubectl get pvc
```
### Deleting mongoDB pod
```bash
kubectl delete pod mongo-deployment-df7b8b9c-kp7t6  
```
<img width="1440" alt="Checking PVC" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/b2f59959-34aa-4c02-b029-d05b894c57da">

## 8. Verifying Data Persistence in MongoDB
<img width="1440" alt="Viewing persisted data inside mongodb" src="https://github.com/Arunodhai/Kaiburr-Task2/assets/60264218/d936a56d-8aec-4ca4-a6d5-c1f6fa778827">
