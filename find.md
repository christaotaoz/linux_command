Author : Chris

### 基本规则：

```
	find   path  -option   [-print] [-exec -ok command ]   {} \;
```

#### -option：

##### 	常用命令：

```
    -name 	根据文件名寻找文件 	 [file_name] 
    -size 	根据文件大小寻找文件	[abs(int)]
    -type 	根据文件类型寻找文件	[f c b l d s]  
```

> `注: f(普通文件) 、c(字符设备文件)、b(块设备文件)、l(符号链接)、d（目录）、s（套接字）`

##### 	基于用户，组搜索：

```
    -user 	根据文件拥有者寻找文件	[user_name] 
    -group 	根据文件所属组寻找文件	[group_name]
    -uid	根据文件拥有者uid寻找文件	[int]
    -gid	根据文件所属组gid寻找文件	[int]
    -nogroup	没有所属组的文件	
    -nouser		没有所属用户的文件
```

##### 	基于权限搜索：

```
	-perm 		根据文件权限寻找文件	[755]
    -executable	文件可执行
    -readable	文件可读
    -writable	文件可写
```



##### 	基于目录深度搜索：

```
	-maxdepth 	[int]
	-mindepth	[int]
```

##### 	基于文件时间搜索：

```
	-atime	访问时间(天)	[int]
	-mtime	修改时间(天)	[int]
	-ctime	变化时间(天)	[int]
	-amin	访问时间(分)	[int]
	-mmin	修改时间(分)	[int]
	-cmin	变化时间(分)	[int]
	-newer	查找比当前文件数据修改时间更加新一点的另外的文件	
	-anewer	查找比当前文件的最后存取时间更加新一点的另外的文件
	-cnewer	查找比当前文件的状态时间更加新一点的另外的文件
```

##### 	逻辑操作符：

```
	-a		与
	-o		或
	-not	非
	!		非
```

##### 	对查找到的文件进一步操作

```
	-exec command {} \;	回车后直接执行
	-ok command {} \;	回车后有是否执行该操作的系统提示
```

##### 	特殊用法(查找含指定字符串的文件)：

```
	find -type d | xargs grep "str" 
	find /home/hadoop/elasticsearch-2.4.3/logs/ -mtime +7 -name “master.log.*” -exec rm -rf {} ;
```

