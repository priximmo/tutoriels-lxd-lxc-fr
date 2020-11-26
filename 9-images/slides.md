%titles: LXC/LXD
%author: xavki

# LXC/LXD : images

<br>


* création d'une image à partir d'un conteneur

```
lxc publish monconteneur --force --alias monimage
```

<br>


* image export

```
lxc image export template_nginx .
tar -xzvf 2e4edbc84669ec313f4d61c3520cf40129cad623b2639614563351f6887b8fe4.tar.gz
```

<br>


* contenu :
			* templates
			* rootfs
			* metadata.yml


```
lxc image import 2e4edbc84669ec313f4d61c3520cf40129cad623b2639614563351f6887b8fe4.tar.gz --alias new
```
