%titles: LXC/LXD
%author: xavki

# LXC/LXD : Port forward

https://www.computersnyou.com/3047/forward-port-lxc-container-quick-tip/


sudo iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j DNAT --to [DestinationIP:PORT]


exemple docker voir iptable d'un conteneur docker
