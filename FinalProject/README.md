# CST8915 Final Project Cloud-Native App for Best Buy

## Student Name: Fayz Reshid

## Student Number: 041066116

### Architecture Diagram

![alt text](image.png)

---

### Project Overview

This project is a multi-service application designed to run on Kubernetes. Each service is containerized, deployed independently, and communicates through internal networking using Kubernetes Services. The goal is to provide a scalable, modular environment that can be deployed locally or in the cloud.

The system includes:

- Backend API services

- Frontend/UI

- Database layer

Each component is packaged as its own Docker image and deployed to Kubernetes using YAML manifests stored in the Deployment Files/ directory.

### Deployment Instructions

#### Prerequisites

Make sure you have the following installed:

- Docker

- kubectl

- AKS or any Kubernetes cluster

#### Build and Push Docker Images

Update image names to match your Docker Hub repo:

docker build -t <dockerhub-username>/<service-name>:latest .
docker push <dockerhub-username>/<service-name>:latest

Repeat for each service in the project.

Deploy to Kubernetes

All YAML files are located under:

/Deployment Files/

To deploy everything at once:

kubectl apply -f "Deployment Files/"

Or deploy individually:

kubectl apply -f Deployment Files/<service-name>-deployment.yaml
kubectl apply -f Deployment Files/<service-name>-service.yaml

Verify Deployment

- Check pods:

kubectl get pods

- Check services:

kubectl get svc

Access the application via the NodePort or Ingress defined in the manifests.

| Service Name     | GitHub Repository                                                                          | Docker Hub Image                                                                                             |
| ---------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| Store Front      | [https://github.com/resh2024/store-front-final]()                                          | [faizz19/store-front-final](https://hub.docker.com/repository/docker/faizz19/store-front-final/general)      |
| Product Service  | [https://github.com/resh2024/product-service-final](https://github.com/yourrepo/service-b) | [faizz19/product-service-final](https://hub.docker.com/repository/docker/faizz19/product-service-final)      |
| Store Admin      | [https://github.com/resh2024/store-admin-final](https://github.com/yourrepo/service-c)     | [faizz19/store-admin-final ](https://hub.docker.com/repository/docker/faizz19/store-admin-final)             |
| Makeline Service | [https://github.com/resh2024/makeline-service-final]()                                     | [ faizz19/makeline-service-final](https://hub.docker.com/repository/docker/faizz19/makeline-service-final)   |
| Order Service    | https://github.com/resh2024/order-service-final                                            | [ faizz19/order-service-final](https://hub.docker.com/repository/docker/faizz19/order-service-final/general) |

---

## Youtube Demo Link

https://www.youtube.com/watch?v=Luc547RXmAM
