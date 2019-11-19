%titles: LXC/LXD
%author: xavki

# LXC/LXD Profile et cloud-init suites...

<br>
* vidéo 14 = config > config de conteneur

* profile = configuration apr défaut de conteneur (modèle)

<br>
* pb init de conteneur puis start

* profile >> appliquer une même instanciation

* cloud-init : attention à l'image (cloud-init) installé

```
lxc image copy images:ubuntu/18.04 local: --alias ubuntu:18.04
```

-------------------------------------------------------------

# Profile et cloud-init


<br>
* création d'un profile

```
lxc profile copy default myprofile
lxc profile edit myprofile
```

Rq : préférez l'injection de fichier (traces)

<br>
* édition de fichier

```
#cloud-config
hostname: xavki
users:
 - name: xavier
packages:
 - nginx
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
```

--------------------------------------------------------------

# Profile et cloud-init

<br>
* injection dans le profile

```
lxc profile set myprofile user.user-data - < preconf.yml
```

<br>
* lancement du conteneur

```
lxc launch ubuntu:18.04 -p default -p myprofile mycontainer
lxc exec mycontainer -- /bin/bash
```


