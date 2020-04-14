# About
The [Ambassador Edge Stack](https://www.getambassador.io) is API Management software. The product has different [editions](https://www.getambassador.io/editions/):
* [Open Source](https://www.getambassador.io/docs/latest/topics/install/install-ambassador-oss/)
* [Community Edition Edge Stack](https://www.getambassador.io/docs/latest/tutorials/getting-started/)
* [Enterprise Edge Stack](https://www.getambassador.io/contact/)

It is described as a "comprehensive, self-service edge stack and API Gateway for Kubernetes built on [Envoy Proxy](https://www.envoyproxy.io/)." -- [getambassador.io](https://www.getambassador.io/docs/latest/)

# Getting Started
This section will get you up and running with Ambassador Edge Stack (AES). AES will be running on local Kubernetes cluster. 

These steps assume OS is Mac OS using:
* [Docker Desktop](https://www.docker.com/products/docker-desktop)
* [Homebrew](https://brew.sh)
If you have a different OS, click [here](https://www.getambassador.io/docs/latest/tutorials/getting-started/).

## Prerequisites
As mentioned, Kubernetes will be used. The [docs](https://kubernetes.io/docs/setup/) mention several different ways to set up a Kubernetes cluster on a local machine. We use [Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/).
1. Install minikube according to [these](https://kubernetes.io/docs/tasks/tools/install-minikube/) instructions.
1. Verify installation use [these](https://kubernetes.io/docs/setup/learning-environment/minikube/#quickstart) instructions.

## Common Minikube Operations
1. Start minikube: `minikube start`
1. List services services: `minikube service list`
1. Stop minikube: `minikube stop`
1. Delete everything in minikube: `minikube delete`


## Install Ambassador Edge Stack
1. startup minikube: `minikube start`
1. deploy ambassador edge stack (AES): `./edgectl install`
1. check ambassador pod is running: `kubectl get pods --all-namespaces`
1. get URLs for AES running in local Kubernetes cluster: `minikube service -n ambassador ambassador --url`
1. The second URL is shown as `http` but is actually `https`

## Launch Edge Policy Console
1. Goto URL: https://IP_ADDRESS:SSL_PORT
1. The browser shows a page that says "Congratulations! You've installed Ambassador Edge Stack", and a link that says "...click here is the quicket way to the Edge Policy Console'. 
1. Click that link
1. The browser shows a page that says "Welcome to Ambassador Edge Stack", and a button that says "COPY TO CLIPBOARD".
1. Click that link
1. The command will resemble: `edgectl login --namespace=ambassador IP_ADDRESS:SSL_PORT`

## Add a proxy
1. Install the quote service according to [these](https://www.getambassador.io/docs/latest/tutorials/quickstart-demo/) instructions.

## Dev Portal
1. https://IP_ADDRESS:SSL_PORT/docs/

# References
* https://www.getambassador.io
* 