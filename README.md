# Helm
Manage values.yaml to set helm

## Repository add
```
helm repo add [NAME] [URL] [flags]
```
```
helm repo add gitlab https://charts.gitlab.io
```
```
helm repo add longhorn https://charts.longhorn.io
```
```
helm repo add matic-insurance https://matic-insurance.github.io/helm-charts
```
```
helm repo add metallb https://metallb.github.io/metallb
```
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
```
```
helm repo add k8s-dashboard https://kubernetes.github.io/dashboard
```
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
```
## Repository update
```
helm repo update
```

## 追加したリポジトリの全てのバージョンを検索
```
helm search repo <reponame>/<chartname> --versions
```
```
helm search repo -l <reponame>/<chartname>
```
```
helm search repo -l gitlab/gitlab-runner
```

## get values
```
helm get values RELEASE_NAME [flags]
```
```
helm get values gitlab/gitlab-runner --revision 1
```
## Install
```
helm install [NAME] [CHART] [flags]
```
```
helm install gitlab gitlab-runner gitlab/gitlab-runnser \
  --version 0.42.0 \
  --namespace gitlab \
  --create-namespace \
  --values values.yaml
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
helm install k8s-dashboard k8s-dashboard/kubernetes-dashboard \
  --version 5.7.0 \
  --namespace kube-system \
  --values values_5.7.0.yaml
```
```
helm install prometheus prometheus-community/prometheus \
  --version 15.10.2 \
  --namespace prometheus \
  --create-namespace \
  --values values.yaml
```
```
helm install circleci-runner matic-insurance/circleci-runner \
  --version 0.1.1 \
  --namespace circleci \
  --create-namespace \
  --values values.yaml
```

## Output values.yaml 
```
helm show values prometheus-community/prometheus --version 15.10.2 > values.yaml
```

## helm list 
```
helm list -A
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