# Project Overview
This project sets up a local Kubernetes environment for deploying core components of a 5G network, demonstrating containerization and Kubernetes configuration for network functions.
Prerequisites

# Docker
# Minikube
# Kubectl
# Basic Kubernetes knowledge

# Environment Setup
1. Install Prerequisites
# Install Docker
# Install Minikube
# Install Kubectl
2. Start Minikube
bashCopyminikube start
# Deployment Components
# MongoDB Database

1) Single instance deployment
2) Persistent data storage
3) Configuration located in mongodb-deployment.yaml

# Network Repository Function (NRF)

3 instances deployed
1) Image: free5gmano/free5gc-control-plane:stage3.1.1-amd64
2) Mount Path: /free5gc/config/nrfcfg.yaml
3) Startup Command: /bin/sh -c sleep 5s && ./bin/nrf

# Access and Mobility Management Function (AMF)

1) 2 instances deployed
2) Image: free5gmano/free5gc-control-plane:stage3.1.1-amd64
3) Mount Path: /free5gc/config/amfcfg.yaml
4) Startup Command: /bin/sh -c sleep 5s && ./bin/amf

# Deployment Instructions
# Create Kubernetes Manifests

1) Create mongodb-deployment.yaml
2) Create nrf-deployment.yaml
3) Create amf-deployment.yaml

# Apply Deployments
`kubectl apply -f mongodb-deployment.yaml`
`kubectl apply -f nrf-deployment.yaml`
`kubectl apply -f amf-deployment.yaml`
#Verify Deployments
`kubectl get pods`
`kubectl get services`
`Troubleshooting`

Check pod logs: 
`kubectl logs <pod-name>`
Verify network connectivity
Ensure correct configuration mounting

