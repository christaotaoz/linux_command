source命令也称为“点命令”，也就是一个点符号（.）,是bash的内部命令。

功能：source 命令会强制执行脚本文件中的全部命令，而忽略脚本文件的权限



source filename 与 sh filename 及./filename执行脚本的区别在那里呢？

1.当shell脚本具有可执行权限时，用sh filename与./filename执行脚本没有区别。

当shell脚本没有可执行权限时，sh filename可以执行 ， ./filename不能执行

2.sh filename 重新建立一个子shell，在子shell中执行脚本里面的语句，该子shell继承父shell的环境变量，但子shell新建的、改变的变量不会被带回父shell，除非使用export。

3.source filename：这个命令其实只是简单地读取脚本里面的语句依次在当前shell里面执行，没有建立新的子shell。那么脚本里面所有新建、改变变量的语句都会保存在当前shell里面。

