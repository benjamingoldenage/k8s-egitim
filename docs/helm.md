# helm

```sh

# Script olarak kurulum, istenirse dağıtımların depolarından da kurulabilir. 
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash

helm version --short

```


```console

helm repo add stable https://kubernetes-charts.storage.googleapis.com/

# helm aktif durumunu çevresel değişken olarak saklar. 
helm env

```

Helm komutu varsayılan olarak kubectl yapılandırmasını kullanır.

```
# helm repoları görelim.
helm repo list

# redis hub sunan helm chars listesi
helm search hub redis

# redis sunan repositoryler. 
helm search repo redis

# redis chart tanımı
helm show chart stable/redis

# redis readme dosyası
helm show readme stable/redis

helm install <kurulum_adi> stable/postgresql

```



Helm ile kendi chartlarımızı oluşturmak

```
helm create ilk-app

```

```
tree ilk-app
ilk-app
├── charts
├── Chart.yaml
├── templates
│   ├── deployment.yaml
│   ├── _helpers.tpl
│   ├── hpa.yaml
│   ├── ingress.yaml
│   ├── NOTES.txt
│   ├── serviceaccount.yaml
│   ├── service.yaml
│   └── tests
│       └── test-connection.yaml
└── values.yaml

3 directories, 10 files
```

```
cat ilk-app/Chart.yaml | grep -v "^#"
apiVersion: v2
name: ilk-app
description: A Helm chart for Kubernetes
type: application
version: 0.1.0
appVersion: 1.16.0

```


```
# Birden çok values dosyası kullanabilirsiniz. Sonra gelen önceliklidir. 
helm install -f myvalues.yaml -f override.yaml  myredis ./redis

```

