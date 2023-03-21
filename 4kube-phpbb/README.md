# 4kube

## Start the minikube cluster

```
minikube start
```

```bash
kubectl apply -f ns.yaml
kubectl apply -f mysql-deploy.yaml
kubectl apply -f mysql-pvc.yaml
kubectl apply -f mysql-secret.yaml
kubectl apply -f mysql-svc.yaml
kubectl apply -f phpbb-deploy.yaml
kubectl apply -f phpbb-svc.yaml
kubectl apply -f phpbb-pvc.yaml
```

```
kubectl delete all --all -n 4kube
```
