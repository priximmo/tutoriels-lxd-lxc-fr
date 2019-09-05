%titles : LXC/LXD
%author: xavki

# LXC/LXD : Sommaire


<br>
* installation facile

```
sudo apt-get install lxd lxd-client
```

puis configuration guidée : accès, mot de passe, stockage et réseau (bridge)

```
sudo lxd init
```

test : 

```
lxd list
```

lancement d'un conteneur :

```
lxd launch alpine monconteneur
```

