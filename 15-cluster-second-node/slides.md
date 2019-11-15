%titles: LXC/LXD
%author: xavki

# LXC/LXD Cluster : Ajout d'un noeud

<br>

* lancement de l'initialisation :

```
lxd init
```

* puis :

```
Would you like to use LXD clustering? (yes/no) [default=no]: yes
What name should be used to identify this node in the cluster? [default=lxc2]: 
What IP address or DNS name should be used to reach this node? [default=10.0.2.15]: 192.168.61.3     
Are you joining an existing cluster? (yes/no) [default=no]: yes
IP address or FQDN of an existing cluster node: 192.168.61.2     
Cluster fingerprint: 3815949190ba074c096453f7fd1b0d2c295111b19b4674968ec7cedb10c00f47
You can validate this fingerpring by running "lxc info" locally on an existing node.
Is this the correct fingerprint? (yes/no) [default=no]: yes
Cluster trust password: 
All existing data is lost when joining a cluster, continue? (yes/no) [default=no] yes
Choose the local disk or dataset for storage pool "default" (empty for loop disk): 
Would you like a YAML "lxd init" preseed to be printed? (yes/no) [default=no]: 
```


---------------------------------------------------------------------------


# Cluster : test


<br>
* liste des noeuds

```
lxc cluster list
lxc list
```

* lancement de 2 conteneurs (équilibre nb conteneurs) :

```
lxc launch e4e574b7c03a c1
lxc launch e4e574b7c03a c2
```
