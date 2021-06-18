# helm charts for install drill-admin, drill-admin-ui, example-app

## Requirements:
- kubectl
- helm
- exist .kube/config - config for kubernetes

## create namespace
```
kubectl create namespace drill
```

## Install drill admin by helm. You need set your URL (admin is web for swagger)
```
URL=drill-admin.10.66.218.100.sslip.io
helm install -n drill --set persistence.enabled=true,ingress.enabled=true,ingress.hosts[0].host=$URL,ingress.hosts[0].paths[0].path=/ drill-admin ./admin
```

## Install drill admin-ui by helm. You need set your URL
```
URL=drill-admin-ui.10.66.218.100.sslip.io
helm install -n drill --set ingress.enabled=true,ingress.hosts[0].host=$URL,ingress.hosts[0].paths[0].path=/ drill-admin-ui ./admin-ui
```

## Install example-app by helm. You need set your URL
```
URL=example-app.10.66.218.100.sslip.io
helm install -n drill --set ingress.enabled=true,ingress.hosts[0].host=$URL,ingress.hosts[0].paths[0].path=/ example-app ./example-app
```


# Yet another install
## Install drill admin by helm. You need set your URL (admin is web for swagger)
```
helm install -n drill --set persistence.enabled=true,ingress.enabled=true,ingress.hosts[0].host=drill-admin.178-154-208-157.my.local-ip.co,ingress.hosts[0].paths[0].path=/ drill-admin ./admin
```

## Install drill admin-ui by helm. You need set your URL
```
helm install -n drill --set ingress.enabled=true,ingress.hosts[0].host=drill-admin-ui.178-154-208-157.my.local-ip.co,ingress.hosts[0].paths[0].path=/ drill-admin-ui ./admin-ui
```

## Install example-app by helm. You need set your URL
```
helm install -n drill --set ingress.enabled=true,ingress.hosts[0].host=exampleapp.178-154-208-157.my.local-ip.co,ingress.hosts[0].paths[0].path=/ exampleapp ./example-app
```