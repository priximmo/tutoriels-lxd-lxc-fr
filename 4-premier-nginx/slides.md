%titles : LXC/LXD
%author: xavki

# LXC/LXD : premier nginx

<br>


* rappel : LXD spécifique aux images systèmes

* ex : installation conteneur système > installation nginx


<br>


* OCI > utilisation d'images dans un format prédéfini

* OCI > tirer une image d'un dépôt(s)

* OCI : image > launch/run > conteneur

------------------------------------------------------------------------

# Nginx

<br>


* utilisation d'une alpine

```
lxc launch monalpine monginx
```

<br>


* installation de nginx en cli

```
lxc exec monginx -- apk update
lxc exec monginx -- apk add monginx
```

-----------------------------------------------------------------------

# Nginx : configuration


<br>


* modification de la conf nginx

```
# ajout root directory
root /var/www/html;

# création du répertoire
mkdir/var/www/html

# lancement de nginx et activation en cas de reboot
/etc/init.d/nginx start
/etc/init.d/nginx status
rc-update add nginx default
```

<br>


* test

```
lxc list #ip
curl <ip>
```
