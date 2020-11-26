%titles: LXC/LXD
%author: xavki

# LXC/LXD : Volumes

<br>


* storage : réservation directory sur le host
		* notamment utilisé sur la création de conteneur

* volume : montage dans un conteneur


* création d'un storage

```
lxc storage create xavki_dir dir source=/home/vagrant/storage
lxc storage volume list xavki_dir
```

* si affectation de tout le conteneur à un storage (type container)

```
lxc profile create xavki
lxc profile edit xavki

devices:
  root:
    path: /
    pool: xavki_dir
    type: disk
```

* création d'un conteneur

```
lxc image copy images:alpine/3.10 local: --alias myalpine
lxc launch myalpine mycontainer -p xavki
lxc storage volume list xavki_dir
```

----------------------------------------------------------------------------------


# LXC/LXD : attach d'un volume


<br>


* création d'un volume dans un storage

```
lxc storage volume create xavki_dir mydata
lxc storage volume list xavki_dir
```

<br>


* attachement du volume

```
lxc storage volume attach xavki_dir mydata mycontainer /tmp
```
