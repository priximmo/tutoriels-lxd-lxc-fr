%titles: LXC/LXD
%author: xavki

# LXC/LXD : GUI - ex : Firefox

<br>


* mapping de votre user dans le conteneur

```
echo "root:$UID:1" | sudo tee -a /etc/subuid /etc/subgid
```

<br>


* création d'un profil lxc

```
lxc profile create gui
```

* édition du profil

```
cat profile.txt | lxc profile edit gui
lxc profile list
```

* lancement du conteneur

```
lxc launch --profile default --profile gui ubuntu:18.04 conteneurgraphique
```

* vérification du cloud init

```
lxc exec gui1804 -- sudo --user ubuntu --login
tail -f /var/log/cloud-init.log
```

* utilisation de firefox en se connectant dans le conteneur ou via la commande exec

```
lxc exec gui1804 -- sudo --user ubuntu --login firefox
```
