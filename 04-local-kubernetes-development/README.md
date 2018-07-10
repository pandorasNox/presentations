
# Template presentation

## start presentation
```
make start-talk
```

## prepare live coding env (e.g.)
```
make env
```


## presentation
Titel: The different shades of local kubernetes development
Abstract:
In a world for developer and cloud native apps we should not forget about our local workflows to keep the developer throuhput smooth and in a flow. Since Kubernetes gained a lot of traction and is currently right in the center of this debate we shall not miss to grasp a look at its local capabilities, workflows, flaws and it's quirks.

#### resources
- kubeadm-dind-cluster
- https://github.com/kubernetes/kubernetes/blob/master/hack/local-up-cluster.sh
- https://blog.digitalocean.com/vault-and-kubernetes/

#### todo - do it incremental
- keep it simple + show code
- incorporate https://de.slideshare.net/berndalter7/kuberwhat-docker-who-a-very-basic-kubernetes-intro
    - call it on slide "Kubernetes basics"
    - maybe have two versions (one with this, one without) or flexible with vertival sliedes etc...
- remove abstract (+ joke / try to think of something new)
- add a section for kubectl (I already did during the presentation - so work this out more clear)
    - how to interact with your cluster
    - get infos ...
- add why local development section ?
- How to seperate it from workplace while keeping it pluggable?
    - have a base version
    - have workplace related versions, branching from the base version ?!
    - is this neccessary or is it just a time snapshot?
    - is git history all I need?
- vagrant - make it working
    - show provisioning
    - maybe rook + PV + PVC concept
- "applications for kubernetes"
    - add grafic !!!
    - maybe start with a reduces view of this topic
        - role / person based
        - 3 roles
        - twist
        - merge all this person into one
            - you want avoid have seperate persons for this
            - explain that this is probbably growth timeline
    - maybe rework it to just skills or so?
- scheduler example
    - add explanaition !!!
    - make own scheduler working
- operator / admission controler example
- write my own => https://github.com/linki/chaoskube/blob/master/chaoskube/chaoskube.go
