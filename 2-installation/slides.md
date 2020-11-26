%titles : LXC/LXD
%author: xavki

# LXC/LXD : installation


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
lxc list
```

<br>



* lancement d'un conteneur :

```
lxc launch images:alpine/3.7 monconteneur
```

