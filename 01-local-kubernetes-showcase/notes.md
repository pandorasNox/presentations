## draft only


- I have a strong developer background

- lets take a look to the big players
    - aws
    - google
    - they want to abstrack the hart parts away
    - its really easy, ok create an account
    - push a button, spin up a cluster
    - talk to the api
    - even the development is fast to a certain point
    - at some points you maybe need to login to your vendor account
    - debugging pielines etc irks

- how local, can we have this local, why we don't have this locals
    - why is it so hard to get this abstraction local?
    - why not per CLI?
    - is it possible?
    - why do we want this (bec its fast)

- what options do we have local, and how does they work? (or does they even worl)

- do you know why docker is so successful?
    - its really developer friendly
    - I mean it has parts that sucks
    - especially the sys ops part in me sees that
    - why do you need a running docker deamon to run / keep container alive?
    - docker is really developer friendly
    - don't get me wrong, I have a strong dev background
    - I love docker
    - I think its really simple to understand
    - it gots 3 core concepts
    - well I would argue 4 but the 4th is also a basic concept you need in other rehards
    - Dockerfiles, Images, Container
    - the foruth network
        - and here again, docker made it really simple to use
        - something like dns for networks
        - how awesome is this
        - you put two container in the same network and yes they can talk
        - and by giving networks a name ist so easy to understand for devs
        - not like this ip stuff

- so kubernetes api also is really friendly
- how can we abstract the setup parts for devs for local env
    - I have an example based on vagrant
    - the makefile is my friend
    - so 
    - irks what is taint, go away
    - but this is the nice about this setup
    - should work on mac's and ubuntu stuff

- but vagrant is not to coool
    - there are reasons to use it
    - graphic how you can get local closer to production
    - vagrant is closer as e.q. minikube
    - there are certain things you can't test local with minikube

- what do you try to achive?
    -  there is two types/reasons for who or why you want do kubernetes local
        - for devs
        - for developent of your kubernetes cluster and testing

- grafic from cubernetes to production close stuff

- minikube, mac, docker edge
    - docker edge
        - also this looks again really cool
        - kubernetes integrated in docker
        - works for me
        - college had problems
        - but is under development
        - when its stable its really awesome

- what you want as a developer is to get access to the kubernetes api
    - means just using kubectl (the "for developer part")

- there is kubernetes for sysadmins and for developers
    - kelsey hightower
    - awesome guy

- why you want it local
    - bring sysOps in the teams
    - go faster local
    - testing
    - also pipelines local at some point if possible

- three ways
    - kubernetes native
    - kubernetes virtualized
        - here we have to mount volumes
        - take care of docker registry
    - kubernetes native/docker based mixed

- we got minikube
    - ubuntu non driver or default driver or virtual box oder kvm
    - mac hyperkit / wirtualbox
- we got kubeadm-dind-cluster
    - sharing local docker images is not so easy, hacky, a workaround, can mess up docker
- we got vagrant (and probably other vortualizer)
    - mounting + docker-registry maybe neccessary

- sometimes you can get around some issues with kubectl set stuff by file nginx config

- also if you introduce one way in your company, you have to choose carfully
    - you want to establish a certain standard
    - so everyone can talk about the same setup
    - solve the same problems only once
    - you don't want to support many different solutions

- you could drive another approch
    - you let it handle the developer
    - they have to establish the api, how they have to care
    - they have to setup somehow the cluster
    - settin the right kubectl context
    - but cluster should work with the application projects
