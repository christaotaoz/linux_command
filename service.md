Name：service - run a System V init script
              The directory containing System V init scripts：/etc/init.d

Usage：

```
service < option > | --status-all | [ service_name [ command | --full-restart ] ]
```

option：

```
-h | --help 	帮助信息
-V | --version 	版本信息
service -V
```

command：

```
service network status 	查看网络服务状态	
service network stop	停止网络服务	
service network start	启动网络服务
(start, stop, restart, try-restart, reload, force-reload, status)
```

