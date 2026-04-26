# nginx-ingress
We will implement the Kubernetes Ingress concept using nginx-ingress on KillerKoda.

# Install Nginx Ingress Controller (Short-Version)
First, we need to install the nginx ingress controller using the following command.
```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml
```

Validate Nginx Ingress Controller is installed successfully
```bash
kubectl get all -n ingress-controller
```
