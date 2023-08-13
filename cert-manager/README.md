# Cert-manager
* Documentation: https://cert-manager.io/docs/installation/helm/

## Add the helm chart repo
```bash
$ helm repo add jetstack https://charts.jetstack.io
$ helm repo update jetstack
```

## Create a Namespace
```bash 
kubectl create namespace cert-manager
```
## If necessary check the avaliable versions for this Helm Chart
```bash
helm search repo jetstack/cert-manager --versions
helm show values jetstack/cert-manager --version=1.12.2
```

# Apply the Custom Resource Definition (CDR) manifest
```bash
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.12.2/cert-manager.crds.yaml

```
## Install cert-manager Helm chart

```bash
helm upgrade -i cert-manager jetstack/cert-manager \
    --namespace cert-manager \
    --version v1.12.2 \
    -f cert-manager-values.yaml
```

## Apply the ClusterIssuer manifest

### before apply change the e-mail on the line 10 of this manifest bellow
```bash
kubectl apply -f ./letsencrypt-clusterissuer.yaml
```