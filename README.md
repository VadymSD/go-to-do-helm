# Go-to-Do Application Using Helm Syntax for Kubernetes

This is a Kubernetes deployment for the to-do application with a REACT frontend and Go backend. MongoDB is used as a database.

## Prerequisites
- Any type of Kubernetes cluster (Minikube or other)
- A started cluster

## Steps to Deploy the Application

### 1. Start a Minikube Cluster
If you are using Minikube, start your cluster with the following command:
```bash
minikube start
```

### 2. Deploy Namespace Using `kubectl`
Apply the Kubernetes namespace:
```bash
kubectl apply -f go-to-do.yaml
```

### 3. Deploy Using Helm
To deploy the application using Helm, execute the following commands:
Install the Helm chart:
```bash
helm install <release_name> mongodb-chart --namespace go-to-do-app
helm install <release_name> backend-chart --namespace go-to-do-app
helm install <release_name> frontend-chart --namespace go-to-do-app
```
Replace `<release_name>` with your desired release name.

### 4. Verify the Deployment
Three sets of pods will be created, allowing you to utilize the full Go-to-Do app functionality. Verify the pods are running with:
```bash
kubectl get pods
```

### 5. Application Reference
For application reference, visit [Link](https://github.com/schadokar/go-to-do-app).
