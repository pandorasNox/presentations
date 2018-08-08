---
title: No one needs a real cluster | Kubernetes - a local path
separator: <!-- ========== ========== ========== -->
verticalSeparator: <!-- ---------- ---------- ---------- -->
theme: sky
revealOptions:
    # transition: 'fade'
---

### No one needs a real cluster

<img
    src="media/kube-logo.svg"
    height="200"
    style=" box-shadow: none; border: none;"
/>

### Kubernetes - a local path

Note:
- test note

<!-- ========== ========== ========== -->

``` shell
$ whoami

name: Tino Stöckel

where                   position
-----------------------------------------------------------
Turbine Kreuzberg GmbH  Platform Engineer
Circus Internet GmbH    Senior Developer / System Operator
Medici Living GmbH      Senior Developer

skills
-----------------------------------------------------------
- Kubernetes            - Ansible           - Gitlab-CI
- Docker                - JavaScript        - Python / Go
...

```

<!-- ========== ========== ========== -->

### Kubernetes @ 
### Turbine Kreuzberg

<img
    src="media/maxi_baremetal.JPG"
    height="400"
    style=" box-shadow: none; border: none;"
/>

Note:
- doin bare metal
- this days with dedicated clouds nodes
- running currently 5 different clusters
- experience with scale

<!-- ========== ========== ========== -->

### a little
### demo app first

<!-- ========== ========== ========== -->

#### CNCF - The Cloud Native Trail Map

<div style="display: flex; justify-content: space-between; align-items: center;">

    <img
        src="media/cncf_trail_map_cut.png"
        height="600"
        style=" box-shadow: none; border: none;"
    />

</div>

Note:
- Cloud Native Computing Foundation
    - create and drive the adoption of a new computing paradigm
    - open source community

<!-- ========== ========== ========== -->

## Kubernetes - why
- k8s api
- k8s automatism
- handles distribution problems

<!-- ========== ========== ========== -->

### It has won:
- Googles GKE (since 2015)
- Microsofts AKS (since 2017)
- Amazons AWS EKS (since 2018)
- DigitalOcean (beta SEP 2018)

<!-- ========== ========== ========== -->

### Kubernetes - what / how
- infrastructure framework
- declarative
- desired state
- kubectl

<!-- ---------- ---------- ---------- -->

### I declare: Hello World!

``` yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 2
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.7.9
        ports:
        - containerPort: 80
```

<!-- ========== ========== ========== -->

<div style="display: flex; justify-content: space-between; align-items: center;">

    <img
        src="media/minikube-logo.png"
        height="200"
        style=" box-shadow: none; border: none;"
    />

    <h4
        style="font-size: 1.3em;"
    >
        <span>kubeadm</span>
        <br />
        <span>-dind-</span>
        <br />
        <span>cluster</span>
    </h4>

    <img
        src="media/virtualbox_logo.png"
        height="245"
        style=" box-shadow: none; border: none;"
    />

</div>

<!-- ========== ========== ========== -->

## minikube
- mainstream tool to run locally
- runs a single-node cluster
- runs in an vm

<!-- ========== ========== ========== -->

#### Install minikube

``` bash
# macOS
brew cask install minikube
```

``` bash
# Linux
curl -Lo minikube \
https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && \
chmod +x minikube && \
sudo cp minikube /usr/local/bin/ && \
rm minikube
```

#### start minikube
``` bash
# uses default driver virtualbox
minikube start
```

<!-- ========== ========== ========== -->

## demo time

<!-- ========== ========== ========== -->

## kubeadm-dind-cluster
- runs a multi-node cluster
- runs in docker
- uses docker-in-docker

<!-- ========== ========== ========== -->

## demo time

<!-- ========== ========== ========== -->

## vagrant
- runs a single/multi-node cluster
- runs in vm's
- closest to real baremetal

<!-- ========== ========== ========== -->

## demo time

<!-- ========== ========== ========== -->

<div style="display: flex; justify-content: space-between; align-items: center;">

    <img
        src="media/minikube-logo.png"
        height="200"
        style=" box-shadow: none; border: none;"
    />

    <h4
        style="font-size: 1.3em;"
    >
        <span>kubeadm</span>
        <br />
        <span>-dind-</span>
        <br />
        <span>cluster</span>
    </h4>

    <img
        src="media/virtualbox_logo.png"
        height="245"
        style=" box-shadow: none; border: none;"
    />

</div>

<!-- ========== ========== ========== -->

### Conclusion

<img
    src="media/mini_baremetal.JPG"
    height="350"
    style=" box-shadow: none; border: none;"
/>

<!-- ========== ========== ========== -->

# Thanks
<div style="font-size: 1em; text-align: left;">

demo app:
<br />
https://github.com/pandorasNox/kubestagram

<br />
<br />

k8s playground:
<br />
https://github.com/pandorasNox/local-kubernetes

<br />
<br />

presentation:
<br />
https://github.com/pandorasNox/presentations
<br />
    => /04-local-kubernetes-development

</div>
