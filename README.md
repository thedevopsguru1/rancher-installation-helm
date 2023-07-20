# rancher-installation-helm
```
helm repo add rancher-latest https://releases.rancher.com/server-charts/latest
```
```
kubectl create namespace cattle-system
```

```
helm upgrade --install rancher rancher-latest/rancher --namespace cattle-system --set hostname=rancher.anaeleboo.com --set bootstrapPassword=admin --set
 ingress.tls.source=letsEncrypt --set letsEncrypt.email=ananae@ex.org --set letsEncrypt.ingress.class=nginx
```
