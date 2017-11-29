# hapi deployment

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/powered-by-electricity.svg)](http://forthebadge.com)

## Purpose

Centos version of the ansible deployment of [Carl Danley's Radium deployment](https://github.com/carldanley/radium-cluster) which is itself based on Kelsey Hightower's [kubernetes the "hard" way](https://github.com/kelseyhightower/kubernetes-the-hard-way).

## Design

![Alt text](/img/hapi.png?raw=true "hapi layout")


## Goals

Running an on-prem Kubernetes cluster on OpenStack. The main goals of these ansible plays are:

1. To deploy and manage a highly available on-prem cluster
1. Demonstrate best practices for running a kubernetes cluster on openstack
1. Keep things clear and simple for others to grok
1. To create an environment that allows fast and scalable deployments of microservices based on the team's needs


## Cluster Specifications

### Software

This cluster bootstraps 3 etcd nodes, 3 kubernetes masters and 3 kubernetes nodes.

| Name | Version |Purpose|
|:-----|:-------|:-------|
| [Cockpit](http://cockpit-project.org/) |  Version 151. | Node and cluster control |
| [romana](http://romana.io/) | 2.0-preview.3 | Automates the creation of isolated cloud native networks and secures them using microsegmentation |
| [kube-dns](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns) | 1.14.4 | DNS Pods and Service on the cluster, other pods in cluster can use the DNS Service’s IP to resolve DNS|
| [rook](https://rook.io/) | 0.5.1 | Rook runs as a cloud-native service for optimal integration with applications in need of storage, and handles the heavy-lifting behind the scenes such as provisioning and management.|

### Caveats

Openstack by default blocks address spoofing; 

Each port (for every node) needs to either:

> Have port_security_enabled set to false 
#### OR
> port-update <port_id_here> --allowed_address_pairs list=true type=dict ip_address=<romana_cidr_here>
