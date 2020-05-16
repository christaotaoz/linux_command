语法

```
sed [OPTION] {script-only-if-no-other-script} [input-file]
```

选项

```
-efhin
-e script, --expression=script
-f | --file	读取包含参数的文件
-h | --help	显示帮助
-i[SUFFIX] 修改源文件 ，提供SUFFIX则会备份
-n | --quiet | --slient	取消默认输出
--version	显示版本
```

命令

```
acdips 
a	新增
c	替换整行
d	删除
i	插入
p	重复打印	和 -n 绑定使用会打印指定内容
s	替换(匹配局部替换)
```

实例

```
sed '2a testContent' test.txt	在第 2 行后面新增一行内容
sed '1,3a testContent' test.txt	在原文的第 1~3 行后面各新增一行内容
sed '2c testContent' test.txt	将第 2 行内容整行替换
sed '2d' test.txt	删除第 2 行
sed '2i testContent' test.txt	在第 2 行前面插入一行内容
sed -n '1,3p' test.txt	只打印第 1~3 行
sed '3,9s/old/new/gi' test.txt	匹配第 3~9 行所有old替换为new
sed -e 's/系统/00/g' -e '2d' test.txt	执行多个指令
sed -f ab.log test.txt	多个命令写进ab.log文件里，一行一条命令，效果同-e
```

温馨提示

```
在指令的开头可以写行号，多行可以用 ',' 分隔
不指定行号,默认对所有行操作
$代表最后一行
指令一般用单引号，指令中有变量的需使用“${}”
替换时指令使用 /old/new/替换参数 格式 ，替换参数有gi！分别表示多个，忽略大小写，非 
```

