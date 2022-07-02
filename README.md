# Helm
Manage values.yaml to set helm

## すべてのバージョンをSerch
```
helm search repo <reponame>/<chartname> --versions
```

## Repository add
```
helm repo add [NAME] [URL] [flags]
```

```
helm repo add longhorn https://charts.longhorn.io
```
```
helm repo add metallb metallb/metallb
```
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
```
```
helm repo add k8s-dashboard https://kubernetes.github.io/dashboard
```

## Repository update
```
helm repo update
```

## Install
```
helm install [NAME] [CHART] [flags]
```

```
helm install longhorn longhorn/longhorn \
  --version 1.2.4 \
  --namespace longhorn-system \
  --create-namespace \
  --values values.yaml
```
```
helm install metallb metallb/metallb \
  --version 0.12.1 \
  --namespace metallb-system \
  --create-namespace \
  --values values.yaml
```
```
helm install ingress-nginx ingress-nginx/ingress-nginx \
  --version 4.1.4 \
  --namespace ingress-nginx \
  --create-namespace \
  --values values.yaml
```
```
helm install kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard \
  --version 5.7.0 \
  --values values_5.7.0.yaml
```

## Unintall
```
helm uninstall longhorn -n longhorn-system
```
```
helm uninstall metallb -n metallb-system
```
```
helm uninstall kubernetes-dashboard
```

## Upgrade
```
helm upgrade longhorn longhorn/longhorn \
  --version 1.3.0 \
  --namespace longhorn-system \
  --values values_v1.3.0.yaml
```
```
helm upgrade ingress-nginx ingress-nginx/ingress-nginx \
  --namespace ingress-nginx --create-namespace \
  --values values.yaml
```