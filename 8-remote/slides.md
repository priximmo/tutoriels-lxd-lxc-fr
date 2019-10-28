%titles: LXC/LXD
%author: xavki

# LXC/LXD : remote

<br>
* accès distant (idem docker)

<br>
* pour :
		* commandes à distance
		* copier des images distantes (comme un dépôt)

<br>
* configuration du lxc distant

```
lxc config edit
config:
  core.https_address: '[::]:8443'
  core.trust_password: true
```

-----------------------------------------------------------

# LXC/LXD : à distance


<br>
* ajout d'un remote 

```
lxc remote add second 192.168.61.2:8443 --password xavki
```

<br>
* utilisation

```
lxc list second:
```

Rq : ne pas oublier les ":"


--------------------------------------------------------------

# LXC/LXD : transfert image


<br>
* transfert d'une image

```
# sur le distant : création de l'image
lxc image copy images:alpine/3.10 local: --alias xavier
```

```
# sur le local : copie de l'image
lxc image copy second:xavier local: --alias xav_second
```

--------------------------------------------------------------

# LXC/LXD : conteneurs


```
lxc launch second:xavier second:conteneur
```
