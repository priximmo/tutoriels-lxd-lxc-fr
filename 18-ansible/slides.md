%titles: LXC/LXD
%author: xavki

# LXC/LXD : ansible et profile

<br>
* cloud init : la bonne conf

```
#cloud-config
hostname: xavki
packages:
  - python
ssh_authorized_keys: 
  - ssh-rsa AAAAB3NzaaC1yc2EAAAADAQABAAAB
write_files:
  - content: |
      172.17.52.32 anothersrv
      127.0.0.1 localhost
      ::1 ip6-localhost ip6-loopback
      fe00::0 ip6-localnet
      ff00::0 ip6-mcastprefix
      ff02::1 ip6-allnodes
      ff02::2 ip6-allrouters
      ff02::3 ip6-allhosts
    path: /etc/hosts
```

---------------------------------------------------------------------

# Conteneur settings


* lancement du conteneur

```
lxc profile set myprofile user.user-data - < preansible.yml 
lxc launch ubuntu:18.04 -p default -p myprofile mycontainer
```

* test ansible

```
ansible all -i "10.124.97.46," -u ubuntu -m ping
```

