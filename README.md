# Kubernetes Full-Stack DevOps Project 

## Overview

This project demonstrates the deployment of a full-stack application on Kubernetes (K3s) running on AWS EC2. The application consists of a frontend, a Node.js/Express backend API, and a PostgreSQL database with persistent storage. The entire deployment is automated using GitHub Actions CI/CD pipelines and container images stored in AWS ECR.

The project also includes HTTPS using Let's Encrypt SSL/TLS certificates, Kubernetes Ingress with Traefik, Docker containerization, and Persistent Volume Claims (PVCs) for database storage.


## Live Application

**Frontend:** https://devops.sunilsinghrajput.in

**Backend API:** https://api.devops.sunilsinghrajput.in


```text
## Architecture

Internet
    │
    ▼
Traefik Ingress
    │
 ┌──┴───────────┐
 ▼              ▼
Frontend      Backend API
                 │
                 ▼
            PostgreSQL
                 │
                 ▼
       Persistent Volume Claim
```
## Tech Stack

* AWS EC2
* Kubernetes (K3s)
* Docker
* AWS ECR
* GitHub Actions
* Node.js & Express.js
* PostgreSQL
* Traefik Ingress Controller
* Let's Encrypt SSL/TLS
* HTML, CSS, JavaScript



## Features

* Full-stack application deployment on Kubernetes
* Automated CI/CD pipelines using GitHub Actions
* Docker image storage in AWS ECR
* HTTPS enabled using Let's Encrypt certificates
* PostgreSQL database with persistent storage
* Rolling updates with zero downtime deployments
* Domain-based routing using Traefik Ingress
* Frontend and backend deployed independently



## CI/CD Workflow

### Backend Pipeline

```text
Git Push
    ↓
GitHub Actions
    ↓
Docker Build
    ↓
Push Image to AWS ECR
    ↓
SSH to EC2
    ↓
Kubernetes Rolling Update


### Frontend Pipeline

Git Push
    ↓
GitHub Actions
    ↓
Docker Build
    ↓
Push Image to AWS ECR
    ↓
SSH to EC2
    ↓
Kubernetes Rolling Update
```

## Kubernetes Components Used

### Deployments

* Frontend Deployment
* Backend Deployment
* PostgreSQL Deployment

### Services

* Frontend Service
* Backend Service
* PostgreSQL Service

### Ingress

* Frontend Ingress
* Backend Ingress

### Storage

* Persistent Volume Claim (PVC)

### Security

* TLS Certificates
* Kubernetes Secrets



## Challenges Solved

### ECR Authentication

Encountered ImagePullBackOff errors while pulling images from private AWS ECR repositories.

Troubleshooting included:

* Investigating pod events using `kubectl describe`
* Testing image pulls using `crictl`
* Diagnosing ECR authentication failures
* Implementing Kubernetes image pull authentication

### SSL/TLS Configuration

Configured HTTPS using:

* cert-manager
* ClusterIssuer
* Let's Encrypt
* Traefik Ingress

### Kubernetes Rolling Updates

Implemented rolling deployments to update applications without downtime.



## Project Structure

kubernetes/
│
├── frontend-deployment.yaml
├── frontend-service.yaml
├── frontend-ingress.yaml
│
├── backend-deployment.yaml
├── backend-service.yaml
├── backend-ingress.yaml
│
├── postgres-deployment.yaml
├── postgres-service.yaml
├── postgres-pvc.yaml
│
└── certificate.yaml


## Screenshots

### Application Running
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/1f0a75a7-977a-4a0a-bab6-cf371f5892c7" />


### HTTPS Enabled
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/eddc320a-e605-4bac-a37d-49cf621df77d" />


### GitHub Actions Successful Deployment

<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/dee5ff63-03a4-4f3f-a05f-c6a5673d9934" />
<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/3ab11639-eb82-40c3-85bc-39642d7ecd2f" />


### Kubernetes Pods Running

<img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/63864ccc-e5f3-4501-af50-4d4c9e74db44" />


---

## Source Code

### Frontend Repository

https://github.com/IM-SUNIL/frontend-demo

### Backend Repository

https://github.com/IM-SUNIL/k8s-express-demo


## Key Learnings

* Kubernetes Deployments, Services, and Ingress
* Persistent Storage using PVCs
* Docker Image Management
* AWS ECR Integration
* GitHub Actions CI/CD
* SSL/TLS with Let's Encrypt
* Kubernetes Troubleshooting
* Rolling Updates and Deployment Strategies
* Private Container Registry Authentication



## Author

Sunil Singh
Systems Engineer | Linux & DevOps Enthusiast
This project was built as a hands-on DevOps learning project covering containerization, orchestration, CI/CD, cloud deployment, networking, storage, and security.
