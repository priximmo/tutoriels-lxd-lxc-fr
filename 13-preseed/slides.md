%titles: LXC/LXD
%author: xavki

# LXC/LXD : init --preseed

<br>
* lancer une installation standardisée

```
config:
  core.trust_password: sekret
  core.https_address: 10.55.60.171:8443
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

https://lxd.readthedocs.io/en/latest/clustering/
