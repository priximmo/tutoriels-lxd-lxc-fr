%titles: LXC/LXD
%author: xavki

# LXC/LXD : move storage

<br>

lxc stop container_name
lxc move container_name temp_container_name -s new_storage_pool
lxc move temp_container_name container_name
lxc start container_name
