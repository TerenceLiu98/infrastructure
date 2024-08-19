# infrastructure

*Using Ansible to manage all my Virtural Machine*

## Daily Update & Upgrade

1. `apt` based server
2. `pacman` based server

## Role specific Installation and Configuration

1. Transit
2. Authoritative DNS Server
3. Kubernetes Cluster


## Structure 

1. `10-base.yaml` - for all server
   1. `apt update` & `apt upgrade`
   2. install basic software: `ipvsadm`, `rsync`, `wireguard-tools`
   3. network optimizing: change to `bbr` & `fq`
2. `20-cluster.yaml` - for cluster master and node
3. `30-transit.yaml` - for transit server and cluster node  
   1. set variables in `defaults/main.yaml`
   2. install `cloudflared` -> `cloudflared.yaml`
   3. install `realm` and start service with icmp monitoring -> `realm.yaml`
   4. copy `wireguard` configuration to corresponding nodes and start wireguard as systemd service

## Others 
* To generate `wireguard` configuration, please go to: [wgtools](https://github.com/TerenceLiu98/wgtools/tree/vxlan)