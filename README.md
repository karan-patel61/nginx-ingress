# nginx-ingress
We will implement the Kubernetes Ingress concept using nginx-ingress on [KillerKoda](https://killercoda.com/playgrounds/scenario/kubernetes).

## Install Nginx Ingress Controller (Short-Version)
First, we need to install the nginx ingress controller using the following command.
```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml
```

## Validate Nginx Ingress Controller is installed successfully
```bash
kubectl get all -n ingress-controller
```

Expected Output:
> root@controlplane:~$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml \
namespace/ingress-nginx created \
serviceaccount/ingress-nginx created \
serviceaccount/ingress-nginx-admission created \
role.rbac.authorization.k8s.io/ingress-nginx created \
role.rbac.authorization.k8s.io/ingress-nginx-admission created \
clusterrole.rbac.authorization.k8s.io/ingress-nginx created \
clusterrole.rbac.authorization.k8s.io/ingress-nginx-admission created \
rolebinding.rbac.authorization.k8s.io/ingress-nginx created \
rolebinding.rbac.authorization.k8s.io/ingress-nginx-admission created \
clusterrolebinding.rbac.authorization.k8s.io/ingress-nginx created \
clusterrolebinding.rbac.authorization.k8s.io/ingress-nginx-admission created \
configmap/ingress-nginx-controller created \
service/ingress-nginx-controller created \
service/ingress-nginx-controller-admission created \
deployment.apps/ingress-nginx-controller created \
job.batch/ingress-nginx-admission-create created \
job.batch/ingress-nginx-admission-patch created \
ingressclass.networking.k8s.io/nginx created \
validatingwebhookconfiguration.admissionregistration.k8s.io/ingress-nginx-admission created \
