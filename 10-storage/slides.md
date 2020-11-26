%titles: LXC/LXD
%author: xavki

# LXC/LXD : storage

<br>


* stockage simple et facile à consulter (diff docker)

* différents types :
		- btrfs (de base)
		- dir (de base)
		- lvm (de base)
		- ceph
		- zfs
		- xfs
		- ...

* exemple à partir de dir


--------------------------------------------------------------------

# LXC/LXD : storage


<br>


* liste des pools de stockage

```
lxc storage list
```

<br>


* détail sur un stockage

```
lxc storage show xavki_dir
```

<br>


* création d'un pool

```
lxc storage create xavki_dir dir source=/home/oki/storage
```

-------------------------------------------------------------------

# LXC/LXD : storage


<br>


* création d'un conteneur sur un pool

```
lxc launch monalpine storeconteneur -s xavki_dir
```

<br>


* suppression d'un conteneur

```
lxc storage delete xavki_dir
```
