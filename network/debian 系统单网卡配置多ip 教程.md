debian系列 单网卡配置多ip 教程

ifconfig #查看网卡名称

vi /etc/network/interfaces	#修改配置文件

```
#source /etc/network/interfaces.d/*

#iface eth0 inet static
auto eth0
iface eth0 inet static
address 192.168.8.82/24
gateway 192.168.8.1
#eth0:0
auto eth0:0
iface eth0:0 inet static
address 10.10.3.82/24

#eth0:1
auto eth0:1
iface eth0:1 inet static
address 192.168.10.82/24

# Local loopback
auto lo
iface lo inet loopback
```

修改好配置文件后重启网络服务

systemctl restart networking

如果没有生效，解决方法

ip addr flush dev eth0

iddown eth0

ifup eth0