# Kubernetes Deployment for Apache and Custom Website

## Installation

### Docker

Install Docker by following the official instructions for your operating system: [Docker Installation](https://docs.docker.com/get-docker/)

### Kubernetes

#### kubectl

Install kubectl using the instructions provided by Kubernetes: [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

#### kubeadm

Install kubeadm using the instructions provided by Kubernetes: [Install kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/)

## Deployment Steps

1. Clone the repository:

```bash
git clone https://github.com/mallasrinivas/docker-jenkins-Apache2.git
cd docker-jenkins-Apache2
```

# Build and push the Docker image

```bash
docker build -t <your-docker-username>/website:v1 .
docker login
docker push <your-docker-username>/website:v1
```

# Apply Apache Deployment

```bash
kubectl apply -f apache-deployment.yaml
````

# Apply Custom Website Deployment

```bash
kubectl apply -f website-deployment.yaml
```

# Create Apache Service

```bash
kubectl apply -f apache-service.yaml
```

# Create Custom Website Service

```bash
kubectl apply -f website-service.yaml
`````
# Apply Ingress configuration

```bash
kubectl apply -f ingress.yaml
```

After completing these steps, your Apache and custom website should be accessible through the Ingress' IP under /apache and /custom paths respectively.
