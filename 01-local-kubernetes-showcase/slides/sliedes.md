---
title: Docker vs Kubernates
separator: <!-- ==================== S ==================== -->
verticalSeparator: <!-- -------------------- V -------------------- -->
theme: solarized
highlight-theme: github
revealOptions:
    # transition: 'fade'
---

## Docker vs Kubernetes
#### A local journey to Kubernetes

<!--
A jouney through a local developer enviroment
A local journey to kubernetes
A local journey to understanding kubernetes
-->

<!-- ==================== S ==================== -->

## A journey to Docker
We rember the pain

<img src="/womm.jpg" height="200" />
<img src="/pape-chaos.jpg" height="200" />
<img src="/parasit.jpg" height="200" />
<img src="/island.jpg" height="200" />

<!-- <table>
<tbody>
<tr>
<td><img src="/womm.jpg" height="150" /></td>
<td><img src="/pape-chaos.jpg" height="150" /></td>
</tr>
<tr>
<td><img src="/parasit.jpg" height="150" /></td>
<td><img src="/island.jpg" height="150" /></td>
</tr>
</tbody>
</table> -->


<!-- ==================== S ==================== -->

> Every environment should be as close to production as possible.


Why?

<!-- <br />
### Also:
- the developer knows the app
- he knows it's deependencies
- he knows what it needs -->

<!-- ==================== S ==================== -->

## Goals
- do the same with kubernetes as with docker
- give you a breave inside to kubernetes
    - kubernetes concepts
    - kubernetes on the CLI

<!-- <img src="/dog-drum.gif" width="400" /> -->

<!-- ==================== S ==================== -->

## But why Kubernetes?

Kubernetes is:
- a framework to
    - orchestrade containers
    - scale containers over nodes

<br />

Kubernetes local brings:
- get closer to production
- a cluster playground
- the understanding / knowledge

<!-- -------------------- V -------------------- -->

> At it's core Kubernetes is a set of small, well defined, components connected by an unified API. On the surface, Kubernetes is an application management platform, but if you dig a little deeper you'll discover that Kubernetes is a framework for building distributed systems.
(Kelsey Hightower)

<!-- ==================== S ==================== -->

## Let's talk Docker

#### A possible workflow with Docker
1. init your project
2. write a <i><b>docker-compose.yml</b></i> file
3. add container related Dockerfiles / configs
4. run:
    ```bash
    docker-compose up
    ```

<!-- -------------------- V -------------------- -->

### Let's do this

#### Coding Time

<!-- -------------------- V -------------------- -->

### So what - recap

- yaml configuration
- run CLI command

<!-- ==================== S ==================== -->

## Sneak peek to Kubernetes

#### Showtime

<!-- -------------------- V -------------------- -->

#### Be patient, I'll show you how in a sec

<!-- ==================== S ==================== -->

## Let's talk Kubernetes

### What you need to know:
- Kubernetes is declarative
- you're declaring the desired state

<!-- -------------------- V -------------------- -->

### How:
- (start cluster)
- write yaml configurations
- execute kubectl on CLI

<!-- -------------------- V -------------------- -->


<img src="/angry-santa.jpg" height="300" />
<img src="/elfs.gif" height="300" />

<!-- -------------------- V -------------------- -->

### Basic concepts

- we're looking into 3 (there are more)
    - pods
    - deployments
    - services

<!-- ==================== S ==================== -->

## Kubernetes - Step by Step

1. setup (local) enviroment
2. yaml configurations
3. do something with <b>kubectl</b>
4. check what went wront
5. repeat 2.

<!-- -------------------- V -------------------- -->

## Local development options

- OSX
    - minikube
    - docker for desktop <i>edge</i> (currently mac only)
    - vagrant / virtualbox
- Linux (Ubuntu)
    - minikube (recommendation: --vm-driver=none)
    - vagrant / virtualbox
    - native kubernetes (complex setup)

<!-- -------------------- V -------------------- -->

## Local development options

### We're still evaluating
- give developers a nice experience
- be it for Ubuntu or for OSX

<!-- -------------------- V -------------------- -->

## Write config's

- we need a <b>deployment</b> (config)
- we need kubectl
<br /><br />
### let's code!

<!-- -------------------- V -------------------- -->

## debug everything

- inspect pods
```
$ kubectl get pods
$ kubectl describe ...
```
- inspect containers
```
$ kubectl log
```
- login to containers
```
$ kubectl exec -it 
```

<!-- -------------------- V -------------------- -->

## FIX config

> Containers within a pod share an IP address and port space, and can find each other via localhost.

<br /><br />
### let's code!

<!-- -------------------- V -------------------- -->

## Write config's

- we need a <b>service</b> (config)
    - servicediscovery !!!
- we need kubectl
<br /><br />
### let's code!

<!-- ==================== S ==================== -->

## Tipp

- Learn you a <b><i>kubectl</i></b>, the rest will emerge

<!-- ==================== S ==================== -->

### Drawbacks

- OSX vs linux
- more boilerplate

<br />

### benefits

- closer to a real cluster
- avoid duplicated maintaining

<!-- ==================== S ==================== -->

## Conclusion
- the main points are
    - <i><b>start</i></b> to understand kubernetes
    - <i><b>start</i></b> to get used to kubectl




- want to show something we currently evaluate
- it's one possible way, no garantees
- but it's a good start point


