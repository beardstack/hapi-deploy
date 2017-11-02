# radium cluster

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/powered-by-electricity.svg)](http://forthebadge.com)

## Purpose

The purpose of this repository is to demonstrate the tooling I use to provision (and manage) my homelab kubernetes cluster &mdash; from scratch. This repository is an adapted approach based on Kelsey Hightower's [kubernetes the "hard" way](https://github.com/kelseyhightower/kubernetes-the-hard-way).

## Goals

Running an on-prem cluster can be difficult &mdash; especially running an on-prem Kubernetes cluster. The main goals of these ansible plays are:

1. To introduce (and manage) a highly available on-prem cluster
1. Demonstrate best practices for running a kubernetes cluster
1. Keep things clear and simple for others to grok

## Cluster Specifications

### Software

This cluster bootstraps 3 etcd nodes, 3 kubernetes masters and 3 kubernetes nodes.

| Name | Version |
|:-----|:-------:|
| [romana](http://romana.io/) | 2.0-preview.3 |
| [kube-dns](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns) | 1.14.4 |
| [influxdb](https://www.influxdata.com/) | 1.3.3 |
| [heapster](https://github.com/kubernetes/heapster) | 1.4.0 |
| [kubernetes-dashboard](https://github.com/kubernetes/dashboard) | 1.7.1 |
| [rook](https://rook.io/) | 0.5.1 |

### Hardware

I built the cluster with the following hardware specifications:

![hardware specs](./documentation/cluster-specs.png)

### Infrastructure Design

![cluster design](./documentation/cluster-design.png)
