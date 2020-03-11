---
marp: false
header: 'Automatic Deployments Relieve Pain and Suffering'
footer: 'Ben Mathews - Kubernetes Salt Lake - March 12, 2020'
paginate: true

---
# **Automatic Deployments Relieve Pain and Suffering**

Vivint's Deployment Pains and how 

* Kubernetes
* Helm,
* Helmfile, 
* and finally Codefresh

...made deployments easy

---

# Ben Mathews

ben@mathews2000.com
TODO github url

--- 

# Who is Vivint (Business)

* We are public now! VVNT
* A leading smart home company in North America. 
* Delivers an integrated smart home system with as 24-7 customer care and monitoring. 
* Dedicated to redefining the home experience with intelligent products and services
* Serves more than 1.5 million customers.

---

# Who is Vivint (Technical)

* 40 Node Kubernetes self hosted cluster
* 140+ Deployments, Daemonsets, Statefulsets, Cronjobs
* 2K+ pods
* 17K (25K peak) messages / second from homes
* 5K messages/second in mobile traffic
* 4+ releases a week

---

# Vivint Deployments - Manual VMs  - Three Years Ago

* Large installation of VMs
* Deployment was a 3-4 hour, completely manual process
* We tolerated problems
* We tolerated pain (speaker notes)

---

# Vivint Deployments - Manual Kubernetes - Jan 2018

* First Kubernetes in production
* Early 2019 shut down the last of the old VM infrastructure

---

# Vivint Deployments - Manual Kubernetes - Jan 2018

## Great

* Deployment faster - under an hour
* More reliable
* Scheduling
* Restart failed processes
* Resource caps
* All the great K8S stuff

---

# Vivint Deployments - Manual Kubernetes - Jan 2018

## But

* But still manual
* Numerous mistakes
* Typing wrong image tag
  * Forgetting to add new parameters
  * Etc.

---

# Manual Kubernetes Complex

* Hand editing YAML configs
* Syncronizing similar deployments across beta and production
* Wanted multiple dev and QA environments
  * Impossible w/ handcrafted YAML

---

# Helm

* Config as code
* Updates/Rollbacks
* Templating

Picture of helm website

---

# Helm public charts

https://hub.helm.sh/

---

# Helm demo

* helm init
* helm deploy
* helm rollback
* helm history

---

# Vivint Deployments - Helm - 2018/2019

## Great 

* Faster - half hour
* Deployments more reliable

---

# Vivint Deployments - Late 2019

## But

* Ops still types helm commands to do deployments
* Still mistakes
  * Once mistakenly applied the beta config to the production deploy

Picture of old confluence page
Long list of helm deploy commands
helm diff -C3 upgrade router-nebo vivint/router --version '0.2.6-release20190820-aab8485' -f k8sconfig/configmap/mrmeseeks/router.yaml --set global.image.tag='6.release-2019-08-20-aab8485'

---

# Helmfile

Engaged Codefresh to resolve these problems

Dustin Van Buskirk suggested Helmfile

* Close the config as code loop

---

# Helmfile demo

TBD

# Vivint Deployments - Helmfile - Late 2019

## Great 

* Faster - 5 minutes
* Deployments more reliable

---

# Vivint Deployments - Helmfile - Late 2019

## But

* Manual workflow 
  * Editing wiki pages
  * Slack messages
  * Miscomunication and mistakes resulted in deployment mistakes and outages
* Still too slow

---

# Product Research

Identified 40+ different CD products
Reviewed them for 
Ability to use existing Helm and Jenkins work
Logging and Audit trails
Okta, Bitbucket Server integration
GitOps style
Ease of use

---

# Product Research – The winners
Argo
Weave Flux
CodeFresh

---

# Codefresh pipeline

---

# Working on

* Liveness & readiness probes
* Helm test
* Breaking up helmfile monolith

---

# Questions