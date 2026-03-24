
## install:
```
helm repo add scidx https://sci-ndp.github.io/scidx-helm
helm repo update
helm upgrade --install scidx scidx/scidx-helm \
  -f my-values.yaml \
  --namespace scidx \
  --create-namespace
```


## local dev:
### install
```
helm dep update ./kafka-kraft
helm dep update ./jupyterhub-helm
helm dep update ./ckan-helm
helm template scidx . -f values.yaml -n scidx > ../ckan-debug
helm dep update
helm upgrade --install scidx . -f values.yaml --namespace scidx --create-namespace
```
## uninstall
```
helm uninstall scidx -n scidx
```
