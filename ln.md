linux创建快捷方式

method1：软链接

```
ln -s mysql-5.7.16-linux-glibc2.5-x86_64 mysql
```

method2：硬链接(默认)

```
ln /home/database.sql /root/db/db.dql
```

- 可以对目录/文件创建软链接,而只能用文件创建硬链接
- 硬链接类似于创建了副本，但又不占用实际空间
- 创建链接的目的可以节省磁盘空间

