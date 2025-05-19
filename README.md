# 🚀 Kubernetes Cluster with Minikube - Task 5 -  For Elevate Labs


This project demonstrates how to build a **Kubernetes Cluster locally using Minikube**, deploy a simple application using **YAML manifests**, and manage it with **kubectl** commands.



---

## 📌 Task Objective

> **Deploy and manage applications on Kubernetes using Minikube, kubectl, and Docker.**

---

## 🛠️ Tools & Technologies

- [Minikube](https://minikube.sigs.k8s.io/)
- [Docker](https://www.docker.com/)
- [kubectl](https://kubernetes.io/docs/reference/kubectl/)
- YAML



---

## ✅ Prerequisites

Make sure the following are installed on your machine:

| Tool      | Version | Command to Check |
|-----------|---------|------------------|
| Docker    | latest  | `docker -v`      |
| kubectl   | latest  | `kubectl version --client` |
| Minikube  | latest  | `minikube version` |

---

## 🔧 Setup & Installation

### 1. Install Minikube (Linux Example)
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube





### ✅ 1. Install Docker

sudo apt install -y docker.io


✅ 2. Install kubectl

sudo snap install kubectl


1️⃣ Start the Minikube Cluster

minikube start


2️⃣ Create a Deployment

deployment.yaml

apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp-container
        image: nginx  
        ports:
        - containerPort: 80





Apply the deployment:

kubectl apply -f deployment.yaml



Expose the App Using Service YAML (service.yaml)

apiVersion: v1
kind: Service
metadata:
  name: myapp-service
spec:
  type: NodePort
  selector:
    app: myapp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80




Apply this Services.

kubectl apply -f service.yaml

To access the service in a browser:

minikube service myapp-service




