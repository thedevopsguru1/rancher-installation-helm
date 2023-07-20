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

```
helm upgrade --install rancher rancher-latest/rancher --namespace cattle-system --set hostname=rancher.anaeleboo.com --set bootstrapPassword=admin --set ingress.tls.source=letsEncrypt --set letsEncrypt.email=ananae@ex.org --set letsEncrypt.ingress.class=nginx
 
```
### IF you use nginx controller
```
helm upgrade --install rancher rancher-latest/rancher --namespace cattle-system --set hostname=app.anaeleboo.com --set bootstrapPassword=admin --set ingress.tls.source=letsEncrypt --set letsEncrypt.email=ananae@ex.org --set letsEncrypt.ingress.class=nginx --set ingress.ingressClassName=nginx
```
