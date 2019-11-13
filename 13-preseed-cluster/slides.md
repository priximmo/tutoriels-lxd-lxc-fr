%titles: LXC/LXD
%author: xavki

# LXC/LXD Cluster : init --preseed

<br>
* lancer une installation standardisée

```
config:
  core.trust_password: monpassword
  core.https_address: 192.168.61.2:8443
  images.auto_update_interval: 15
storage_pools:
- name: default
  driver: dir
networks:
- name: lxdbr0
  type: bridge
  config:
    ipv4.address: 192.168.100.14/24
    ipv6.address: none
profiles:
- name: default
  devices:
    root:
      path: /
      pool: default
      type: disk
    eth0:
      name: eth0
      nictype: bridged
      parent: lxdbr0
      type: nic
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
