%titles: LXC/LXD
%author: xavki

# LXC/LXD : module ansible

<br>


* attention module lxc n'est pas à jour (lxc<2.0)

* utiliser le module lxd_container
https://docs.ansible.com/ansible/latest/modules/lxd_container_module.html

* vagrant activation ssh :

```
vim /etc/ssh/sshd_config 
service ssh restart
```

----------------------------------------------------------------

# Ansible : create container


<br>


* édition du playbook

```
- name: deploy container
  hosts: all
  become: yes
  tasks:
  - name: create container
    lxd_container:
      name: xavki
      source:
        type: image
        mode: pull
        server: https://images.linuxcontainers.org
        protocol: lxd
        #alias: ubuntu/bionic/amd64
        alias: alpine/3.10/amd64
      wait_for_ipv4_addresses: true
```


* lancement du playbook

ansible-playbook -i "192.168.61.2," -u vagrant -k create.yml

---------------------------------------------------------------------

# Ansible : remove container


<br>


* playbook

```
- name: remove container
  hosts: all
  become: yes
  tasks:
  - name: remove
    lxd_container:
      name: xavki
      state: absent
```
