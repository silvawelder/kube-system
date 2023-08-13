# Ingress-nginx Controller 
* Documentation: https://github.com/kubernetes/ingress-nginx

## Add the helm chart repo
```bash
$ helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
$ helm repo update ingress-nginx
```

## Create a Namespace
```bash 
kubectl create namespace ingress-nginx
```
## If necessary check the avaliable versions for this Helm Chart
```bash
helm search repo ingress-nginx --versions
helm show values ingress-nginx/ingress-nginx --version=4.7.0
```

## Install Ingress-nginx Helm chart

```bash
helm upgrade -i ingress-nginx ingress-nginx/ingress-nginx \
    --namespace ingress-nginx  \
    --version=4.7.0 \
    -f ingress-values.yaml
```