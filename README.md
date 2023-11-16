# Minikube MongoDB and MongoDB Express Deployment

This project demonstrates how to deploy MongoDB and MongoDB Express within a Minikube cluster using Kubernetes. The deployment includes secret management, configuration maps, and services to expose the MongoDB and MongoDB Express instances.

## Prerequisites

- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Deployment Steps

1. **Start Minikube:**
   ```bash
   minikube start
   ```
2. **Apply Secrets:**
   ```bash
   kubectl apply -f mongo-secret.yaml
   ```
3. **Deploy MongoDB:**
   ```bash
   kubectl apply -f mongo.yaml
   ```
4. **Deploy MongoDB Service:**
   ```bash
   kubectl apply -f mongo-service.yaml
   ```
5. **Deploy MongoDB ConfigMap:**
   ```bash
   kubectl apply -f mongo-configmap.yaml
   ```
6. **Deploy MongoDB Express:**
   ```bash
   kubectl apply -f mongo-express.yaml
   ```
7. **Deploy MongoDB Express Service:**
   ```bash
   kubectl apply -f mongo-express-service.yaml
   ```
8. **Access MongoDB Express:**
   ```bash
   minikube service mongo-express-service
   ```

## YAML Files Overview

 `mongo-secret.yaml`
Contains the MongoDB authentication credentials as base64-encoded values.

 `mongo.yaml`
Defines the MongoDB Deployment, specifying replicas, labels, and environment variables from the secret.

 `mongo-service.yaml`
Defines the MongoDB Service to expose the MongoDB deployment.

 `mongo-express.yaml`
Defines the MongoDB Express Deployment, specifying replicas, labels, and environment variables from the secret.

 `mongo-express-service.yaml`
Defines the MongoDB Express Service as a LoadBalancer to expose the MongoDB Express deployment externally.

 `mongo-configmap.yaml`
Defines the ConfigMap for MongoDB Express, containing the database URL.

## Cleanup
To delete the deployed resources:

```bash
   To delete the deployed resources:
   ```

