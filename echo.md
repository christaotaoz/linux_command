#注意符号

```
result=`df -h` 
echo "$result" > a.txt
```

将命令的输出结果作为一个变量写入到指定文件

| command > file  | 将输出重定向到 file。                              |
| --------------- | -------------------------------------------------- |
| command < file  | 将输入重定向到 file。                              |
| command >> file | 将输出以追加的方式重定向到 file。                  |
| n > file        | 将文件描述符为 n 的文件重定向到 file。             |
| n >> file       | 将文件描述符为 n 的文件以追加的方式重定向到 file。 |
| n >& m          | 将输出文件 m 和 n 合并。                           |
| n <& m          | 将输入文件 m 和 n 合并。                           |
| << tag          | 将开始标记 tag 和结束标记 tag 之间的内容作为输入。 |

- 标准输入文件(stdin)：stdin的文件描述符为0，Unix程序默认从stdin读取数据。

- 标准输出文件(stdout)：stdout 的文件描述符为1，Unix程序默认向stdout输出数据。

- 标准错误文件(stderr)：stderr的文件描述符为2，Unix程序会向stderr流中写入错误信息。

  实例：

  ```
  command 2 > file	#将标准错误写入file文件(注意会覆盖)
  command > file 2>&1	#将标准错误和标准输出合并后写入file文件	>&表示合并操作
  command < infile > outfile	#从infile文件读数据 后 写入outfile文件
  command << delimiter
      document
  delimiter		#读取分隔符之间的文档
  command > /dev/null	#丢弃 该内容
  ```

  