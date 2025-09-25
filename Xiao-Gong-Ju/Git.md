# Git  
## 1. git的常用命令 
- git init  初始化一个 git 仓库
- git add .  把当前环境下的所有更改都添加到暂存区，需要在最后面加一个 . ，如果想添加单个文件，把点换成文件名即可
- git commit -m "XXX"   把暂存区的修改推送到本地仓库，XXX就是 commit message，需要用简洁的语言描述文件的修改（做了什么）
- git push （-u origin master）  把本地仓库的更改推送到远程仓库，首次提交应带上 -u origin master，其中，是否是 master 应根据上游的分支名称来确定，有一些是 main
- git pull 使本地和远程仓库的内容同步
- git branch 查看所有的分支，带 * 的分支为当前所在的分支 
     - git branch <分支名>  创建名为 XXX 的分支，但不会切换到该分支
     - git branch -d <分支名> 删除分支，大写 D 表示强制删除
- git checkout -b branch 创建并切换到新分支，branch 是新分支名
- git switch 切换分支
     - git switch -c <新分支名>  创建并切换到新分支，和 git checkout -b branch 作用一样
     - git switch -  切换到上一个分支

## 2. Github CLI 
是 Github 官方的命令行工具，有[官方文档](https://cli.github.com/manual/)可以学习
