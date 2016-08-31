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

In this post we will explore deploying a [gRPC](http://grpc.io/) server and client to a [kubernetes](http://kubernetes.io/) cluster.  We will primarily take advantage of Service Discovery, but several Kubernetes features will be used in our solution.

## Setup

The <abbr title="Kubernetes">k8s</abbr> contributors have poured a ton of work into [minikube](https://github.com/kubernetes/minikube) which makes it trival to stand up a local k8s cluster.  We'll be able to get a local cluster setup with two steps. Impressive.

### Install kubectl
```
OS X:
    curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/v1.3.0/bin/darwin/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/
LINUX:
    curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/v1.3.0/bin/darwin/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/
```

### Install minikube
```
OS X:
    curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.6.0/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
LINUX:
    curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.6.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

You should now be able to run:

> kubectl get nodes

And see a list simular to this:

```bash
NAME         STATUS    AGE
minikubevm   Ready     1d
```

While we are in the terminal lets setup a project structure to house the content from the rest of this post.

```bash
mkdir -p deploying-grpc-services-to-kubernetes/operations/{deployments,services,config-maps}
mkdir -p deploying-grpc-services-to-kubernetes/{services/hello,api/hello, protos}

cd deploying-grpc-services-to-kubernetes
git init

cd api/hello
npm init -y
cd ../../
cd services/hello
npm init -y
npm i --save grpc
cd ../../
```

## (Preparing for deployment)

## Coding the services

As we are not here for a deep dive into gRPC let's use the hello world sample service. First we'll download the protobuf description.

> curl -Lo protos/helloworld.proto https://raw.githubusercontent.com/grpc/grpc/master/examples/protos/helloworld.proto

Then pull in the server implementation;

> curl -Lo services/hello/index.js https://raw.githubusercontent.com/grpc/grpc/master/examples/node/dynamic_codegen/greeter_server.js


- write code for server
- write code for client
- create containers

## (writing kubernetes files)

- write deployments
- write services

## Release the hounds

- launch deployments
- launch services