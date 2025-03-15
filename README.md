# Frontend Application

This repository contains the source code and configuration files for the frontend application. The application is built using React and served using Nginx in a Docker container. Kubernetes manifests are also provided for deployment.

## Table of Contents
1. [Project Structure](#project-structure)
2. [Prerequisites](#prerequisites)
3. [Getting Started](#getting-started)
4. [Building the Docker Image](#building-the-docker-image)
5. [Deploying to Kubernetes](#deploying-to-kubernetes)
6. [Configuration](#configuration)
7. [License](#license)

---

## Project Structure
.
├── src/ # Source code for the React application
├── .dockerignore # Files to ignore when building the Docker image
├── Dockerfile # Dockerfile for building the frontend image
├── frontend-configMap.yaml # Kubernetes ConfigMap for frontend configuration
├── frontend-deployment.yaml # Kubernetes Deployment for the frontend
├── frontend-ingress.yaml # Kubernetes Ingress for routing traffic to the frontend
├── frontend-service.yaml # Kubernetes Service for exposing the frontend
├── nginx.conf # Nginx configuration file
├── package.json # Node.js dependencies and scripts
└── README.md # Project documentation


---

## Prerequisites

Before you begin, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v16 or higher)
- [Docker](https://www.docker.com/) (v20 or higher)
- [Kubernetes](https://kubernetes.io/) (optional, for deployment)
- [kubectl](https://kubernetes.io/docs/tasks/tools/) (optional, for Kubernetes deployment)

---

## Getting Started

1. Clone the repository:
   git clone git@github.com:dbd311/frontend-multicloud.git
   cd frontend-multicloud
   
2. Install dependencies:
    npm install

3. Start the development server:
    npm start

## Building the Docker Image

To build the Docker image for the frontend application:

1. Build the Docker image:
    docker build -t frontend:latest .

2. Run the Docker container locally:
    docker run -p 80:80 frontend:latest

3. Open your browser and navigate to http://localhost:80 to view the application.

## Deploying to Kubernetes

The Kubernetes manifests provided in this repository can be used to deploy the frontend application to a Kubernetes cluster.

1. Apply the Kubernetes manifests:
    kubectl apply -f frontend-configMap.yaml
    kubectl apply -f frontend-deployment.yaml
    kubectl apply -f frontend-service.yaml
    kubectl apply -f frontend-ingress.yaml

2. Verify the deployment:
    kubectl get pods
    kubectl get services
    kubectl get ingress
    
3. Access the application through the Ingress or Service endpoint.

## Configuration

1. Nginx Configuration

    The nginx.conf file contains the Nginx configuration for serving the React application. You can modify this file to customize the server behavior.



2. Kubernetes Manifests

    frontend-configMap.yaml: Contains environment-specific configuration for the frontend.

    frontend-deployment.yaml: Defines the Kubernetes Deployment for the frontend application.

    frontend-service.yaml: Exposes the frontend application as a Kubernetes Service.

    frontend-ingress.yaml: Configures the Ingress for routing external traffic to the frontend.






