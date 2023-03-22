# Exam 4kube

## Launch project without environment gesture

```bash
# Create resources with environment gesture
kubectl apply -k ./4kube
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
kubectl delete -k ./4kube
# Or force delete all resources to clean up
kubectl delete all --all -n 4kube
```

## Deployment with environment gesture (Kustomize)

With Kustomize, you can totally make patches in the base configuration code in the 4kube folder.

So, you can adjust your deployment depending the needs of the environment.

```bash
# Create resources with environment gesture
kubectl apply -k ./envs/local
# Expose web prestashop service
minikube service service-prestashop -n 4kube --url
```

### Delete project

```bash
# Delete resources
kubectl delete -k ./envs/local
# Or force delete all resources to clean up
kubectl delete all --all -n 4kube
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

## Manage Flux with Helm Release

### Notes

Does not work but here are my sources :
https://fluxcd.io/flux/guides/helmreleases/
https://github.com/fluxcd/flux2-kustomize-helm-example
Follow the installation path depending your OS : https://fluxcd.io/flux/installation/

Wouldn't it be easier in 3 hours to deploy using kustomizations envs files with patchs to resources ?

### Create Flux namespace

```bash
kubectl create ns flux
```

### Export github credentials

```bash
export GHUSER="NathanRodet"
```

### Launch flux
