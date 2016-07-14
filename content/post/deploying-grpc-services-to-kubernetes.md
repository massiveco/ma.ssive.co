---
author: "Dan Williams"
comments: true
date: "2016-07-13T00:18:25-04:00"
draft: true
slug: "deploying-grpc-services-to-kubernetes"
tags: ["grpc", "kubernetes"]
title: "Deploying gRPC services to kubernetes"
---

## Introduction

In this post we will explore deploying [gRPC Services](http://grpc.io/) to a [kubernetes](http://kubernetes.io/) cluster.  We will primarily take advantage of Service Discovery, but several Kubernetes features will be used in our solution.

## Setup

The <abbr title="Kubernetes">k8s</abbr> contributors have poured a ton of work into [minikube](https://github.com/kubernetes/minikube) which makes it trival to stand up a local k8s cluster.  We'll be able to get setup with two steps. Impressive.

### Install minikube
```
OS X:
    curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.5.0/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
LINUX:
    curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.5.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

## (Preparing for deployment)

- write code for server
- write code for client
- create containers

## (writing kubernetes files)

- write deployments
- write services

## Release the hounds

- launch deployments
- launch services