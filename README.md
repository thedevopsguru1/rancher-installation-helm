# rancher-installation-helm
### Make sure to install cert-manager and nginx-controller
https://github.com/thedevopsguru1/deploy-ingress-controller-tls-certificate
## Install Rancher

```
helm repo add rancher-latest https://releases.rancher.com/server-charts/latest
```
```
kubectl create namespace cattle-system
```
### Use this and make sure the host name is the proper one
```
helm upgrade --install rancher rancher-latest/rancher --namespace cattle-system --set hostname=rancher.anaeleboo.com --set bootstrapPassword=admin --set ingress.tls.source=letsEncrypt --set letsEncrypt.email=ananae@ex.org --set letsEncrypt.ingress.class=nginx --set ingress.ingressClassName=nginx --create-namespace

```

## If running into error : use this 
https://github.com/thedevopsguru1/rancher-local-helm
