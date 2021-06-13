# helm charts for install drill-admin, drill-admin-ui, example-app

## create namespace
```
kubectl create namespace drill
```

## install drill admin by helm
```
helm install -n drill --set persistence.enabled=true,ingress.enabled=true,ingress.hosts[0].host=drill-admin.10.66.218.100.sslip.io,ingress.hosts[0].paths[0].path=/ drill-admin ./admin
```

## install drill admin-ui by helm
```
helm install -n drill --set ingress.enabled=true,ingress.hosts[0].host=drill-admin-ui.10.66.218.100.sslip.io,ingress.hosts[0].paths[0].path=/ drill-admin-ui ./admin-ui
```

## install example-app by helm
```
helm install -n drill --set ingress.enabled=true,ingress.hosts[0].host=example-app.10.66.218.100.sslip.io,ingress.hosts[0].paths[0].path=/ example-app ./example-app
```
