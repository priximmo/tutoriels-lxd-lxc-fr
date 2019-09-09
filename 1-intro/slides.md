%titles : LXC/LXD
%author: xavki

# LXC/LXD : Introduction


<br>
* outil de virutalisation linux, 2014 (docker 2013)

<br>
* basé sur les linux containers

* respect et utilisation OCI (Open Container Initiative)

* au début utiliser par docker pour implémenter des conteneurs linux

* analogie entre les commandes et principes : similitudes et mieux comprendre

* lxc : léger (C) différent de runC (Go)

* lxd : API qui utilise lxc, développée par cannonical (ubuntu)

* lxd : CLI, sécurité, réseau, stockage

* exemple : Nova Openstack

* un sujet en transparence : la sécurité via les privilèges d'accès (cGroup et namespace)

* différence lxd/lxc = container system (virtualise un système : debian, alpine, ubuntu...)

------------------------------------------------------------------------------


# Différence avec docker et CRI-O


<br>
* imbrication des process

Docker > containerd (+ shim avant) > runC > linux containers (process + isolation cgroups namespaces...)

CRI-O > containerd > runC > ...

Lxd > Lxc > ...

<br>
* dédié aux conteneurs système (debian, ubuntu, centos...)

<br>
* beaucoup de similarités dans les commandes et principes (OCI oblige)

* des choses mieux aussi
