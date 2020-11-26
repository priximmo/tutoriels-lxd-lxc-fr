%titles: LXC/LXD
%author: xavki

# LXC/LXD Cluster : init --preseed

<br>


* lancer une installation standardisée

```
config:
  core.https_address: '[::]:8443'
  core.trust_password: xavier
networks:
- config:
    ipv4.address: auto
    ipv6.address: auto
  description: ""
  managed: false
  name: lxdbr0
  type: ""
storage_pools:
- config: {}
  description: ""
  name: default
  driver: dir
profiles:
- config: {}
  description: ""
  devices:
    eth0:
      name: eth0
      nictype: bridged
      parent: lxdbr0
      type: nic
    root:
      path: /
      pool: default
      type: disk
  name: default
cluster:
  server_name: node1
  enabled: true
```

* lancement

```
cat <preseed-file> | lxd init --preseed
```

-----------------------------------------------------------------

# Cluster

* test accès distant : 

```
lxc remote add second 192.168.61.2:8443 --password xavki
lxc launch images:alpine/3.10 monconteneur
lxc list second:
lxc launch second:e4e574b7c03a second:monconteneur2
lxc remote remove second
```

https://lxd.readthedocs.io/en/latest/clustering/
