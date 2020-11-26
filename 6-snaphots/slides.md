%titles: LXC/LXD
%author: xavki

# LXC/LXD : Snapshots

<br>



* liste des infos sur un conteneur

```
lxc info monconteneur
```

<br>


* modification d'un conteneur

```
lxc exec monconteneur -- sh
```

<br>


* création d'un snaphost

```
lxc snapshot monconteneur step1:v1.1
```

<br>


* restauration du snapshot

```
lxc restore monconteneur step1:v1.1
```

