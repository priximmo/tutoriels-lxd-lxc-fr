%titles : LXC/LXD
%author: xavki

# LXC/LXD : premier conteneur alpine


<br>
* rappel : LXD spécifique aux images systèmes

* ex : installation conteneur système > installation nginx


<br>
* OCI > utilisation d'images dans un format prédéfini

* OCI > tirer une image d'un dépôt(s)

* OCI : image > launch/run > conteneur

------------------------------------------------------------------------

# Les images

<br>
* lister les images présentes localement

```
lxc image list
```

<br>
* copie d'une image (docker pull...)

```
lxc image copy images:alpine/3.5 local: --alias monalpine
lxc image list
``` 

------------------------------------------------------------------------

# Les conteneurs


<br>
* même principe que docker on lance/run à partir d'une image

```
lxc list
```

Rq : les infos utiles (ip)

<br>
```
lxc launch monalpine monconteneur
```

Rq : pas de "-d"

<br>
* se rendre dans un conteneur

```
lxc exec monconteneur -- /bin/ash
```

<br>
* lancer une commande depuis l'extérieur

```
lxc exec monconteneur -- hostname
```

