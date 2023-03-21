# Exam 4kube

## Launch project

```bash
# Create resources
kubectl apply -k 4kube-exam
# Expose web prestashop service
minikube service service-prestashop -n 4kube --url
```

### Output :

|-----------|--------------------|-------------|---------------------------|
| NAMESPACE | NAME | TARGET PORT | URL |
|-----------|--------------------|-------------|---------------------------|
| 4kube | service-prestashop | http/80 | http://192.168.49.2:30080 |
|-----------|--------------------|-------------|---------------------------|

## Delete project

```bash
# Delete resources
kubectl delete -k 4kube-exam
```

## Debug / Monitoring

### Dashboard

```
minikube dashboard --url
```

### CLI Logs

```bash
# Get pods
kubectl get pods -n 4kube
# Get logs
kubectl get logs <pods>
```
