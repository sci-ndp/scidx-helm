end goal:
all subchart will be hosted on github page;
user only need to do:
1. 'helm add scidx-stack <chart_url>' 
2. 'helm repo update'
3. provide the parent level values.yaml just like ./scidx-helm/values.yaml
    helm install scidx scidx-stack/scidx-stack -n scidx --create-namespace -f my-values.yaml


cd scidx-helm
### optional: (this will be packaged into tgz in prod)
```
helm dep update ./kafka-kraft
helm dep update ./jupyterhub-helm
helm dep update ./ckan-helm
```
### install
```
helm template scidx . -f values.yaml -n scidx > ../ckan-debug
helm dep update
helm upgrade --install scidx . -f values.yaml --namespace scidx --create-namespace
```
### uninstall
```
helm uninstall scidx -n scidx
```
