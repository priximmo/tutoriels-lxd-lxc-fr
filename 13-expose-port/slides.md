%titles: LXC/LXD
%author: xavki

# LXC/LXD : exposition de ports

<br>
lxc config device add publishcontainer myport80 proxy listen=tcp:0.0.0.0:8888 connect=tcp:127.0.0.1:80
