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

1. `10-base.yaml` for basic update 
2. `20-transit.yaml` for transit server 
   1. set variables in `defaults/main.yaml`
   2. install `cloudflared` -> `cloudflared.yaml`
   3. install `realm` and start service with icmp monitoring -> `realm.yaml`