# nginx-ingress
We will implement the Kubernetes Ingress concept using nginx-ingress on [KillerKoda](https://killercoda.com/playgrounds/scenario/kubernetes).

## Install Nginx Ingress Controller (Short-Version)
First, we need to install the nginx ingress controller using the following command.
```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml
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

## Validate Nginx Ingress Controller is installed successfully
```bash
kubectl get all -n ingress-controller
```
> root@controlplane:~$ kubectl get all -n ingress-nginx 
NAME                                           READY   STATUS      RESTARTS   AGE
pod/ingress-nginx-admission-create-tlxkn       0/1     Completed   0          6m15s
pod/ingress-nginx-admission-patch-cbnx6        0/1     Completed   1          6m15s
pod/ingress-nginx-controller-f86fd6d96-s7mhs   1/1     Running     0          6m15s

NAME                                         TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)                      AGE
service/ingress-nginx-controller             LoadBalancer   10.107.152.143   <pending>     80:30496/TCP,443:31299/TCP   6m15s
service/ingress-nginx-controller-admission   ClusterIP      10.106.47.143    <none>        443/TCP                      6m15s

NAME                                       READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/ingress-nginx-controller   1/1     1            1           6m15s

NAME                                                 DESIRED   CURRENT   READY   AGE
replicaset.apps/ingress-nginx-controller-f86fd6d96   1         1         1       6m15s

NAME                                       STATUS     COMPLETIONS   DURATION   AGE
job.batch/ingress-nginx-admission-create   Complete   1/1           10s        6m15s
job.batch/ingress-nginx-admission-patch    Complete   1/1           11s        6m15s

