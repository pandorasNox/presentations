
Title ideas:
- the different shapes of local kubernetes development
- local kubernetes workflows


- ?
    - did you remember the last time you played a video game?
        - discovert a dangeon
        - enabled new equipment
        - which brought you to a hole new level?
        - something which turned the world upside down?

- what is kubernetes?
    - "" 
    - it has a huge share of ops work

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