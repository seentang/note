# git 说明

>为啥选用git，而不是svn

## git服务器搭建  Gogs

## git客户端配置

## git client命令

- 创建代码库，配置文件，提交第一份代码
- 克隆版本库，下载修改代码
- 提交修改，合并冲突典型工作流程
 -- git status 查看更改
 -- git add 添加修改过文件
 -- git  commit -m “xxxx” 提交修改并添加注释 
 -- git pull       拉取最新代码
 -- git mergetool   合并冲突
 -- git add .  提交合并后的最新代码
 -- git rebase --continue 合并刚刚的两次commit为一次 commit，净化版本历史
 -- git push 把本地分支合并好的最新代码，提交到远程代码仓库
- git log 查看历史
- git checkout 导出指定版本 指定文件  git checkout \<hash\> \<filename\>
