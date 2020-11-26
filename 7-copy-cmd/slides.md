%titles: LXC/LXD
%author: xavki

# LXC/LXD : Copy containers / Publish

<br>


* 2 méthodes :
			* copy : copier/coller de conteneur
			* publish : création d'une image puis lancement


<br>


* méthode COPY (sans arrêt de la source)

```
lxc copy <conteneur_source> <conteneur_destination>
lxc start <conteneur_destination>
```

<br>


* méthode PUBLISH (création d'image mais arrêt source)

```
lxc publish monginx --alias template_nginx --force
lxc launch template_nginx <conteneur_destination>
```
