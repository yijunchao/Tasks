# 第二阶段——如何使用git
## 创建版本库
1.创建空目录
在git bash 中输入$ mkdir learngit $ cd learngit $ pwd
2.将这个目录变成Git可以管理的仓库
输入$ git init进行初始化
3.将文件直接添加到版本库中
使用命令 git add告诉git将文件添加到本地仓库，再使用git commit-m" "将文件进行提交
-m后写的是本次提交的说明    **git commit 是一次提交多个文件的命令，所以可以一次性add多个文件**
***添加某个文件时，该文件必须在当前目录下存在***

## 关于 版本库管理
### 查看文件状态
要随时掌握工作区的状态，使用git status命令。
如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
### 版本回退
1.使用git log查看版本提交历史，命令显示从最近到最远的提交日志，
使用git relog查看版本命令历史，确定需要的“未来“版本
2.关于git版本的表示，在git中我们用HEAD表示当前版本，HEAD^表示上一个版本，当版本太过于靠前时可以用HEAD^n表示第n个版本
3.回退指令 ：$git reset --hard HEAD^n
在历史版本中来回：$git reset --hard commit _id _
4.关于commit _id _:是提交文件的版本号，它是一个SHA1计算出来的一个非常大的数字，用十六进制表示，而每提交一个新版本，实际上Git就会把它们自动串成一条时间线。

## 远程仓库
将GitHub的仓库与本地仓库相连接
### 添加远程仓库
1.添加密钥
远程传输过程是一个加密的传输，需要在GitHub上进行ssa的验证
先使用git bash创建自己的密钥，$ ssh-keygen -t rsa -C "youremail@example.com"
再将文件中的公钥与GitHub进行验证
2.建立连接
使用指令$ git remote add origin git@github.com:name/learngit.git
再将本地文件远程传输到远程使用指令$ git push -u origin master
-u参数代表的是将本地分支与远程分支相连接，以后推送时可以时指令更加简化
当文件在本地提交后再次进行只需要输入$ git push origin master即可
### 克隆仓库
克隆指的是将GitHub的远程仓库复制到自己的本地仓库，使用指令$ git clone git@github.com:name/仓库名.git


