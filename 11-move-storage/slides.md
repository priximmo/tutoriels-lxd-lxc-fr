%titles: LXC/LXD
%author: xavki

# LXC/LXD : move storage

<br>
* migration sur un autre volume - astuce

* impossible normalement (utilisation remote)

* réorganisation

* utilisation d'un conteneur intermédiaire

* arrêt/relance du conteneur et manipulation

<br>
* lancement de la socket

```
lxc config edit
config:
  core.https_address: '[::]:8443'
  core.trust_password: true
```

* ajout remote

```
lxc remote add replica 127.0.0.1:8443 --password monpassword
```

Rq: écoute sur tous les ports

---------------------------------------------------------------

# LXC/LXD : copy du conteneur


* création conteneur

```
lxc image copy images:alpine/3.10 local: --alias myalpine
lxc launch myalpine mycontainer
```

* création d'un storage

```
lxc storage create xavki_dir dir source=/home/vagrant/storage
```

* création d'un profile

```
lxc profile create xavki
lxc profile edit xavki

devices:
  root:
    path: /
    pool: xavki_dir
    type: disk
```

* Migration à froid

```
lxc stop mycontainer
lxc copy replica:mycontainer mycontainerV2 -p xavki
lxc storage show xavki_dir
```

