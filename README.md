markdown

# Nginx Demo App

A clean, production-ready Kubernetes application managed with **Helm**.

## Features
- Helm v3 chart
- Configurable replicas, image, resources
- Horizontal Pod Autoscaler (HPA)
- ConfigMap & Secret management
- Ingress support (optional)
- Best practices (labels, namespaces, templating)

## Quick Start

```bash
# 1. Start a local cluster (Minikube/Kind/Docker Desktop)
minikube start

# 2. Install the chart
helm install demo . --namespace demo-app --create-namespace

# 3. Access the app
kubectl port-forward svc/demo-service 8080:80 -n demo-app

Then open http://localhost:8080Commandsbash

helm upgrade demo . -n demo-app          # Update after changes
helm uninstall demo -n demo-app          # Remove
helm lint .                              # Validate chart

Project Structure

my-app/
├── Chart.yaml
├── values.yaml
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── configmap.yaml
│   ├── namespace.yaml
│   ├── secret.yaml
│   ├── hpa.yaml
│   └── ingress.yaml
└── README.md

Made with  using Helm best practices.

---

