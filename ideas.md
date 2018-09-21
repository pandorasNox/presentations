
# ideas

- demystify kubernetes rbac
- JamStack architecture
- admission controller mutating/validating webhooks
- project based cli's
- local CI/CD
- react-core-filer / property-selector
- static-site enterprise recommendations deconstructed
- static-site CI/CD edge case(s)
- learn to automate the setup of a bare metal k8s cluster
- how I approched vue.js and its ecosystem
- fail fast
- SSL demystified (k8s context, web context)

## 04 - split talk
- tools for local kubernetes development
- evolutional app development with kubernetes
- kubernetes traffic distribution example (why) ???
- minikube is not enough - local development with k8s

## admission controller
k8s basics
admission controller / k8s api workflow
problems / goal / aim
k8s Quality of Service (QoS) Classes
resources-webhook logic matrix
resources-webhook implementation
how to run the admission controller in a cluster (MutatingWebhookConfig explained)

utopia planitia setup
why we did it this way
kublet and the manifestsfolder
ansible + ssl setup + generating the MutatingWebhookConfig
