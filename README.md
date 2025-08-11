# Kubernetes Cluster Setup with Minikube

## Overview
This project demonstrates how to set up a local Kubernetes cluster using Minikube, deploy a sample Nginx application, and manage it using basic Kubernetes commands. Perfect for beginners learning Kubernetes fundamentals!

## Install kubectl (Kubernetes CLI)
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

## Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

## :hammer: Prerequisites
- Docker installed 
    Run the following command to install docker (for ubuntu) *sudo apt install docker.io*
- Minikube installed
- kubectl installed
- 4GB+ RAM available

## :rocket: Quick Start

1. Start Minikube Cluster

**bash**

*minikube start --driver=docker*

2. Verify Cluster Status
- *minikube status*
- *kubectl get nodes*

Should show 1 node named *minikube* with status *Ready*

3. Deploy Nginx Application
- Create a deployment.yaml file
- Run the following command to apply the deployment. *kubectl apply -f deployment.yaml*

4. Expose the service
- Created a service.yaml file
- Run the following command to apply the service. *kubectl apply -f service.yaml*

5. Access your Application
- Run the below command and access the URL in your browser keeping the terminal open while browsing

*minikube service nginx-service --url*

6. Scaling the Application
- Run the below command to scale the application

*kubectl scale deployment nginx-deployment --replicas=4*
- Check the Pods

*kubectl get pods*

*It will show 4 pods*




    
