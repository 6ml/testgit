##GIT学习
####安装
`windows`下使用`exe`应用程序安装GIT

全局配置：
```
git config --global user.name ''

git config --global user.email ''
```
####基本操作
#####创建版本库：
版本库又叫仓库，`repostory`，这个目录里的所有文件都可以被GIT管理起来，每个文件的修改，删除，GIT都能跟踪，可以在任何时刻追踪历史，还可以回退版本。

创建版本库，将当前目录编程GIT可以管理的仓库，使用该条命令后会在当前目录内常见一个`.git`目录，这就是版本库。
```
git init
```
#####常用操作
将文件添加到暂存区
```
git add readme.txt
```
将暂存区中的文件提交到仓库
```
git commit -m '说明'
```
查看是否有改变
```
git status
```
查看文件具体改变内容
```
git diff readme.txt
```
#####版本回退
查看提交历史记录
```
git log //会显示每次提交的版本号、anthor、时间、提交说明

git log --pretty=oneline //让每条记录显示在一行
```
版本回退
```
git reset --hard HEAD^^ //回退一个版本

git reset --hard HEAD~num //回退num个版本
```
版本恢复
```
git reflog //显示所有版本号

git reset --hard versionId //跳到版本号为versionId的版本
```
#####理解工作区与暂存区
**工作区**：就是电脑里的目录(.git隐藏目录版本库除外)
**版本库**：工作区有一个隐藏目录.git，这个不属于工作区，这是版本库。版本库里存了很多东西，最重要的就是`stage`(暂存区)，还有GIT为我们自动创建了第一个分支`master`，以及指向`master`的一个指针`HEAD`。
#####撤销和删除文件
**撤销修改：**
-	手动更改需要修改回来的东西，然后`add`到暂存区，再`commit`
-	用`reset`版本回退
	```
	git reset --hard HEAD^^
	```
-	用`checkout`丢弃工作区的修改
	```
	git checkout -- file //将file在工作区做的修改全部撤销
	```
	-	未放入暂存区：使用撤销修改会 ++撤销所有修改++
	-	已放入工作区：撤销修改只会 ++撤销放入暂存区后的修改++

**删除操作：**
```
git rm test.txt //将文件从工作区和暂存区中删除

git rm --cached test.txt //从暂存区删除文件但工作区中不删除
```
删除后可以用`git add`将文件增加回来，或者`git commit`

删除后在没有`commit`之前可以用`checkout`撤销删除。

重命名工作区文件：
```
git mv test.txt test2.txt
```



####windows里DOS命令
移动到目标目录：`cd url`
查看目录中文件：`dir`
创建文件夹：`mkdir`
创建空文件：`cd.a.txt` `copy nul a.txt` `type nul>a.txt` `echo a 2>a.txt`
**没有输出，重定向到新文件**
创建非空文件：`echo a>a.txt` `type a.txt>b.txt` `copy a.txt b.txt`
打开记事本：`notepad`
查看文件：`type a.txt`
删除单个文件：`del a.txt`
删除文件夹：`del D:\packet` `rd D:\packet`
`del`**只能删除文件，**`rd`**只能删除空文件夹**
修改文件名：`ren text.txt text2.txt`
移动文件：`move E:\test\text.txt E:\test`
复制文件：`copy E:\test\text.txt E:\test`

定时关机：`shutdown.exe -s`马上关机，`shutdown.exe -s -t num`定时关机，`shutdown.exe -r`关机并重启，`shutdown -h`休眠，`shutdown -l`注销当前用户
打开任务管理器：`taskmgr`


