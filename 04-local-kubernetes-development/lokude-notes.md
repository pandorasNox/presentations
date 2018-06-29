
Title ideas:
- the different shapes of local kubernetes development
- local kubernetes workflows

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

what kind of workflow do you need (based on your position)

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
