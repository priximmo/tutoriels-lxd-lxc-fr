%titles: LXC/LXD
%author: xavki

# LXC/LXD Profiles

<br>
* profile = configurations par défaut pour container

* config = une sous partie (cloud init)

<br>
* profile default

```
lxc profile list
lxc profile show default
lxc profile copy default myprofile
lxc profile show myprofile
```

<br>
* deux modes : 
			* CLI
			* fichier de configuration

--------------------------------------------------------------


# LXC : Profile configuration


<br>
* CLI - exemple

```
launch myalpine mycontainer -c security.privileged=true
```

Rq : https://lxd.readthedocs.io/en/latest/containers/

<br>
* CLI - check/ config

```
lxc config edit mycontainer
```

-------------------------------------------------------------

# Cloud-Init


<br>
* création d'un conteneur

```
lxc init ubuntu: mycontainer
```

<br>
* fichier config.yml

```
#cloud-config
hostname: myhost
users:
- xavki
packages:
- nginx
write_files:
  - content: |
      Hello première ligne
      Deuxième ligne
    path: /tmp/xavki.txt
```

<br>
* édition de sa configuration

```
lxc config set mycontainer user.user-data - < config.yml
```

* lancement du conteneur

```
lxc start mycontainer
lxc exec mycontainer -- /bin/bash
```

---------------------------------------------------------------


