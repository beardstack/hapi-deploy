# hapi deployment

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/powered-by-electricity.svg)](http://forthebadge.com)

## Purpose

Centos version of the ansible deployment of [Carl Danley's Radium deployment](https://github.com/carldanley/radium-cluster) which is itself based on Kelsey Hightower's [kubernetes the "hard" way](https://github.com/kelseyhightower/kubernetes-the-hard-way).

## Goals

Running an on-prem Kubernetes cluster on OpenStack. The main goals of these ansible plays are:

1. To introduce (and manage) a highly available on-prem cluster
1. Demonstrate best practices for running a kubernetes cluster
1. Keep things clear and simple for others to grok

## Cluster Specifications

### Software

This cluster bootstraps 3 etcd nodes, 3 kubernetes masters and 3 kubernetes nodes.

| Name | Version |Purpose|
|:-----|:-------:|:-------:|
| [Cockpit](http://cockpit-project.org/) |  Version 151. | Node and cluster control |
| [romana](http://romana.io/) | 2.0-preview.3 |Romana automates the creation of isolated cloud native networks and secures applications using microsegmentation|
| [kube-dns](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns) | 1.14.4 |:-------:|
| [influxdb](https://www.influxdata.com/) | 1.3.3 |:-------:|
| [heapster](https://github.com/kubernetes/heapster) | 1.4.0 |:-------:|
| [rook](https://rook.io/) | 0.5.1 |:-------:|

