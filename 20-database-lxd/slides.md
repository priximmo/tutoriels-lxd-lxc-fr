%titles: LXC/LXD
%author: xavki

# LXC/LXD : la database

<br>


https://blog.nanjj.cn/lxd.html
* lxd dispose d'une base sqlite

<br>



* deux types de schémas : 
		* local : accessible uniquement depuis le noeud
		* global : accessible depuis tous les noeuds du cluster

* liste des tables de global :

```
lxd sql global .schema
```

* idem pour local :

```
lxd sql local .schema
```

-----------------------------------------------------------------------

# Requêtes


<br>


* liste des conteneurs

```
lxd sql global 'select * from containers;'
```


<br>


* liste des images

```
lxd sql global 'select * from images;'
```

<br>


* liste des profiles

```
lxd sql global 'select * from profiles;'
```

<br>


* liste des configs de profiles

```
lxd sql global 'select * from containers_config;'
```
