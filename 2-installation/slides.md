%titles : LXC/LXD
%author: xavki

# LXC/LXD : Sommaire


<br>
* installation facile

```
sudo apt-get install lxd lxd-client
```

<br>
* configuration guidée : accès, mot de passe, stockage et réseau (bridge)

```
sudo lxd init
```

<br>
* test : 

```
lxd list
```

<br>

* lancement d'un conteneur :

```
lxd launch alpine monconteneur
```

