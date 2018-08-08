# CLI-CHEAT-SHEET

## start talk
``` bash
cd ~/src/github.com/pandorasnox/presentations/04-local-kubernetes-development

make start-talk

```

## demo app intro

``` bash
cd ~/src/github.com/pandorasnox/kubestagram/

code .

# explain struct

# start kubestaback + curl
cd ~/src/github.com/pandorasnox/kubestagram/kubestaback

# change env file cors = false

docker-compose up

# curl get
curl http://localhost:22080

# curl post image
cd ~/Downloads/example_img/ && curl -i -X POST -H "Content-Type: multipart/form-data" -F "imgdata=@example.jpg" http://localhost:22080

# curl get
curl http://localhost:22080


############################## start kubestafront

cd ~/src/github.com/pandorasnox/kubestagram/kubestafront

docker run -it --rm -v $(pwd):/temp -w /temp -p 3000:3000 node:8.11.3-alpine sh

# check browser console

# fix kubestaback - cors

# upload images

```

### minikube
``` bash

# get infos
## set context
kubectl config use-context minikube

# build workflow
## kubestaback
cd ~/src/github.com/pandorasnox/kubestagram/kubestaback

### show yaml

### build
eval $(minikube docker-env)
docker build -t kubestaback:v1 .

### deploy
kubectl apply -f kubernetes/namespace.yaml 
kubectl apply -f kubernetes/

cat /etc/hosts | grep minikube

### check
curl minikube/kubestaback

## kubestafront
cd ~/src/github.com/pandorasnox/kubestagram/kubestafront

### build dist
docker run -it --rm \
-v $(pwd):/temp \
-w /temp \
-e IMAGE_SERVICE_URL="http://minikube/kubestaback" \
-e SITE_ROOT="http://minikube" \
-e BASE_PATH="kubestafront" \
node:8.11.3-alpine \
sh -c 'yarn build'

### build img in minikube
eval $(minikube docker-env);
docker build -t kubestafront:$(V) $(PWD)
docker run -it -v $(shell pwd):/temp -w /temp node:8.11.3-alpine sh -c 'rm -rf dist'

### deploy
kubectl apply -f kubernetes/namespace.yaml -f kubernetes/

### visit http://minikube/kubestafront/

# mount flow

## kubestaback

### delete old deploy
kubectl delete -f kubernetes/


### create mount

### deploy
kubectl apply -f kubernetes/namespace.yaml -f kubernetes/dev/

### follow app logs
kubectl -n kubestaback logs PODNAME -c kubestaback -f

### change file

```

### dind

``` bash

# switch context
make context

# talk distribution feature

# deploy example nginx
kubectl apply -f /example/nginxapp/nginxapp.yaml

# check
kubectl -n nginxapp get po
kubectl -n nginxapp get po -o wide
watch kubectl -n nginxapp get po -o wide

# new terminal
kubectl drain kube-node-3

# watch the magic

```

### vagrant
``` bash

### deploy kured

### deploy nginxapp

### set file

### watch

```

