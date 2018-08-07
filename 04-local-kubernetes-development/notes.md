
Title ideas:
- local Kubernetes development
- Noone needs a (real) cluster
- Noone cares for a real cluster
- Noone cares for your cluster
- Noone cares for a cluster
subtitle:
- local Kubernetes development


- today I want to tak about three topics
    - kubernetes
    - (developer) workflow
    - local development

- do I have to explain container?
    - ...

- what is kubernetes?
    - is an amazing abstraction layer over your hardware
    - kubernetes lets tread the underlaying data-center as one massive computer
    - Kelsey Hightower
        - Kubernetes is an infrastructure framework. It's YAML based configuration files and the kubectl command line tool make it approachable to developers, but far from the developer productivity you find in a PaaS or FaaS platform.
        - Docker wrote the developer story. Kubernetes expanded the narrative and added some new chapters, but the story has no ending.
        - Kubernetes is a framework for bulding distributed platforms
    - sits right above the hardware layer
        - abstracts it completly
    - treads nodes as just resources
    - concepts
        - declarative - YAML based configuration
            - describe the **desired state**
            - 
        - contract
        - container runtime is the contract
            - packagin
    - its a collection of different tools
        - which follow conventions
        - each of these components is pluggable and exchangable
        - best example is the network layer
            - weave
            - flannel
            - ...
    - resource concept
        - nodes / pods / services
        - ...

How or even can this integrate with our local workflow?

- (developer) Workflow
    - I want to talk about workflow

- what are you doing local
    - write some code
    - have some sorts of env
    - check it
        - tests (watch)
        - in the browser
        - postman
        - db client

- docker 
    - I want to talk about docker
    - docker is the precessor to kubernetes
    - do you know why it is / was so successful?
        - first of it did something really clever with LXC
        - clever packaging around this technologie
        - but there is more
        - simple base concept
            - Dockerfile
            - docker image
            - docker container
        - sitenote: its always the talk about container eg. container runtime
        - provides
            - the right friendly tools
            - the right firendly workflow

- another example
    - cloud providers
    - aws, google, digitalocean
    - build a very high abstraction over infrasturcture
    - even more, they provide easy acces for developers
        - via gui
        - via api's
-----

If we talk about workflow
we also have to ask
- what kind of role do I fullfill
- what kind of workflow needs this role?

what kind of workflow do you need (based on your role)

-----

... and yet again, I'll talk about workflow
- make it easy for you developers
    - provide them with a nice workflow

- a question to ask
    - what is your role?
    - what are you going to do with the cluster?
    - what are you try to accomplish?

- kubernetes presents itsel on different layers/levels
    - kubernetes for application developer
    - kubernetes for SysOps
    - kubernetes for kubernetes developers
    - ... probably more 

- we are living in the time of cloud native apps

- why would you want to have it locally?

- 3 options
    - minikube / docker-for-desktop (edge)
    - kubeadm-dind-cluster
    - vagrant

- minikube
    - overview
        - singlenode cluster
        - works with different drivers
        - today --vm-driver=virtualbox
    - workflows
        - vm driver
        - none driver
    - showtime (what could go wrong)

- kubeadm-dind-cluster
    - overview
        - docker based
        - uses docker-in-docker (dind)
        - multinode
        - fixed
    - workflow
    - showtime

- vagrant
    - overview
        - most close to simulate a real cluster
    - workflow
    - showtime

- docker workflow vs kubernetes workflow

- workflows
    - mount volumes vs docker registry

- tooling to ensure smooth workflow
    - make
    - bash
    - go




- as your knowledge related to kubernetes grows
    - you want to get closer to your live setup






- why local development
    - Personal Research
    - experiemnts
    - fast feedback
        - fast failiur
    - reproducible
    - don't influence others
        - if you broke it, none will notice
    - it's like beta testing
    - theoreticly no internet needed (if you cach everything, even e.g. deb pkg)
    - it's cheap

- did your every thoght about how much different your local env looked
    - over the years
    - could have looked
    - and how this effected / would have effected your workflows ?

- did you maybe some day lent back and thought
    - how great are IDE's this days
    - how great there integrate applications

- I hate if something has flaws or feels unnatural

- certified kubernetes
    - get closer to => avoid "works on my machine"

- having a test cluster besides your production one is favorable
    - sometimes you just don't have the resources
    - you can't just put new stuff on your production cluster
    - 

- if I can't run it locally with open source software, go away
    - if it can't run in docker
    - if it can't run via vm

- kubernetes architecture
    - kubernetes
        - nothing to magical about that
        - the fun starts after that
        - now you start to think a little more about architecture
    - ingress
    - persistent volume
        - the apps should be able to create pvc's
    - docker-registry (depends)

- pv
    - can to apps use the same pv
    - how does the pc organize this if its possible?
        - reattaching, how does it work?

============

- we want always get as close to production as possible
    - why ...
- we also want thinks to be reproducable and automated
    - if something breaks and it hurts, it's not well automated

============

anecdoetes

- ?
    - did you remember the last time you played a video game?
        - discovert a dangeon
        - enabled new equipment
        - which brought you to a hole new level?
        - something which turned the world upside down?

======

why or why not to do bare metal
- you have the financial resources
- you don't need the bare metal process power
- you don't need a special kubernetes infrastructure

=====

so the differend shades

I created the following graphic
and what you may or may not want to do is think a little about
- your role
- what you try to accomplish

- as you can see there are strict zones and overlapping zones

example
- first I show you a really simple example with docker
    - deploying two services who talk to each other
    - the steps are
        - ensure docker runs
        - write a docker-compose file or bash file for your services
        - run docker-compose up
- as application developer
    - we can mirror similar steps with just minikube
        - and actually each other cluster size
    - steps are
        - start cluster and ensure is running
        - write some yaml configuration
        - apply the configuration
    - if you check now
        - same result as with docker
    - not really complicated
    - just enough for application developers
    - only a little yaml overhead

========

- goal is to provide a nice workflow basic
- fortunatly developers are clever
    - they'll integrate this in ther personal workflow
    - or find something for them which fits better for them
    - maybe something which can influence a new basic setup
- on the other hand it's nice to give developers something simple like a
    - make setup
    - e.g. frontend developers
        - who never got in contact with ops related tasks yet
- your developers won't take days to spin up a setup

========

we advocat for
    - each developer has diff entry levels
    - each team should have a kube dev eventually
    - each developer get the opportunity to develop this skills

- you want that in your teams
    - bright spectrum from dev to ops skills
    - want that this knowledge / spectrume exists acroos the teams

========

- kubernetes
    - gives you an amazing abstraction over you infrastructe
        - let's see and treat all you little server as they were one giant computer
    - it's declarative
        - uses configuration as code
        - describing a desired state
        - kubernetes is doing the rest
    - gives you an amazing API thanks to kubectl

=======

- examples (by roles)
    - delpoy app, mount volume
    - deploy app + docker-registry
    - create a certain kubernetes structure
    - deploy operator

- examples by tools
    - minikube
        - app deploy
    - kubeadm-dind-cluster
        - sheduler deploy
    - vagrant
        - ...

======

- conclustion
    - bring coffee, mate and pizza

- conclusion
    - enable your devs to run a local cluster
    - think about what you want to achive
    - provide a basic workflow

=========

- kubernetes wants you to look at resources
    - but from the view from the application
    - not the view of the infrastructure
- infrastructre says
    - this is my limit
- app says
    - this is what I need
- kubernetes takes care to match it

=========

depth application developers needs to understand kubernetes
- not completely sure
- something like this:
    - kubectl
        - deploy + debug
    - nodes
    - dns
    - ingress
    - services
    - deployments
    - pods

drive
- intrinsic nature

when minikube is not enough
- scheduler
- operators
- controllers
- state / storage
