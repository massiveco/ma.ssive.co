---
author: "Dan Williams"
comments: true
date: "2016-07-13T00:18:25-04:00"
draft: true
share: true
slug: "deploying-grpc-services-to-kubernetes"
tags: ["grpc", "kubernetes"]
title: "Deploying gRPC services to kubernetes"
---

## Introduction

In this post we will explore deploying [gRPC Services](http://grpc.io/) to a [kubernetes](http://kubernetes.io/) cluster.  We will primarily take advantage of Service Discovery, but several Kubernetes features will be used in our solution.