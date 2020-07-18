常用命令：

```
systemctl list-units --type=service | grep network	#查找所有或某个服务

systemctl list-unit-files | grep enable	 #查看所有启动项或开机启动项

systemctl status network.service #查看服务状态

systemctl start network.service #启动服务

systemctl restart network.service #重启服务

systemctl stop network.service #停止服务

systemctl enable network.service #开机启动服务

systemctl disable network.service #停止开机启动

systemctl --failed #列出所有失败单元

systemctl kill network.service #杀死服务

systemctl list-unit-files --type=mount #列出挂载点

systemctl start tmp.mount

systemctl stop tmp.mount

systemctl restart tmp.mount

systemctl reload tmp.mount

systemctl status tmp.mount

```

#常用服务

```
firewalld.service
```

