#### **Git适合多人配合代码开发，有备份，协同开发，版本设定，版本选择等功能。**

- 开源的代码管理工具
- 分布式管理工具（更安全,可以脱网操作）
- git的分支处理更加便捷
- 代码的传输更新速度更快

#####  安装：

```
#	sudo  apt-get install git
```

##### 配置：

```
#	git config --system  	系统中所有用户都使用的配置(/etc/gitconfig)
#	git config --global 	用于当前用户的配置(~/.gitconfig)
#	git config  		用于当前项目的配置(.git/config)
```



##### 常用：

```
#	git config --system  user.email ‘XX@XX’		配置邮箱
#	git config --global  user.name  Levi		配置用户名称
#	git config core.editor	'xx'			配置编辑作者
#	git config --global credential.helper store	记住账号密码
#	git config --system --unset credential.helper	账号输入错误，重置输入
#	git remote add origin XX.git			连接远程仓库
#	git push -u origin master			推送代码
#	git clone XX.git				从远程获取代码
#	git init					创建本地仓库
#	git status					查看分支状态
#	git add file					提交指定文件到暂存区
#	git add --all					提交所有改动到暂存区
#	git commit file -m ‘XX’				同步到仓库
#	git log						查看日志
#	git checkout  --  readme.txt			撤回改动
#	git mv  git_test  test/				移动文件
#	git rm  git_test				删除文件
#	git reset  --hard  HEAD^			退回到上个commit位置
#	git reset  --hard  commit_id			退回到指定的commit位置
#	git reflog					获取所有 commit_id
#	git reset  --head  commit_id			去往指定的版本
#	git remote add [<options>] <name> <url>		连接远程库，name是为远程库命名

```

##### 临时保存工作区:

```
#	git stash apply stash@{2}			让工作区退回到指定的保存状态
#	git stash clear					删除所有的工作区
#	git stash					保存现有工作区内容，回到上一个commit状态
#	git stash list					查看现在保存的工作区 0是最近保存的工作区
#	git stash pop					工作区退回到上一个保存的状态并删除上一个保存工作区

```

##### 分支管理：

```
#	git branch			查看分支 （*为当前正在工作的分支）
#       git branch  -a                  查看所有分支
#	git branch dev			创建一个dev分支
#	git checkout dev		切换到dev分支工作
#	git checkout -b dev		创建dev分支并切换到dev
#	git merge dev_Tom		合并指定分支
#	git branch -d dev_Tom		删除分支  （如果分支没有合并则用-D删除）

```

##### 标签管理(在commit上打标签)：

```
#	git tag  v0.9 commit_id  打在指定commit上
#	git tag  v1.0            打在最近一个版本上
#	git reset --hard v1.0    退回到某一个标签
#	git tag -d v1.0          删除标签

```

FAQ

```
1.执行完commit后，想撤回commit，怎么办？
答: git reset --soft HEAD^
    这样就成功的撤销了你的commit，注意，仅仅是撤回commit操作，您写的代码仍然保留。
    HEAD^的意思是上一个版本，也可以写成HEAD~1
    如果你进行了2次commit，想都撤回，可以使用HEAD~2

    git reset 参数：
    --soft  
    	不删除工作空间改动代码，撤销commit，不撤销git add . 
    --mixed 
    	意思是：不删除工作空间改动代码，撤销commit，并且撤销git add . 操作
    	这个为默认参数,git reset --mixed HEAD^ 和 git reset HEAD^ 效果是一样的。
    --hard
    	删除工作空间改动代码，撤销commit，撤销git add . 
    	退回到指定版本
    --head
    	去往指定的版本(更早或之后)

2.如果commit注释写错了，只是想改一下注释怎么办？
答：git commit --amend
   此时会进入默认vim编辑器，修改注释完毕后保存就好了。

```

