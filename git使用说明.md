# git 说明

[TOC]

>为啥选用git，而不是svn

## git服务器搭建  Gogs

### [gogs下载](https://gogs.io/docs/installation/install_from_binary)

- 下载解压 命令行跳转到gogs根目录
- 运行gogs.exe web
- 打开 localhost:3000/install 按提示就行配置
- [配置windows service](https://gogs.io/docs/installation/run_as_windows_service)

## git客户端配置

### 保存用户密码

项目目录下 .git/config  增加
[credential]
helper = store
> git config credential.helper store

### 对比工具配置

> 以配置DiffMerge为例  在C:\Users\当前用户\.gitconfig 增加
[diff]
tool = diffmerge
[difftool "diffmerge"]
cmd = C:/Program\\ Files/SourceGear/Common/DiffMerge/sgdm.exe \"$LOCAL\" \"$REMOTE\"
[merge]
tool = diffmerge
[mergetool]
keepBackup = false
[mergetool "diffmerge"]
trustExitCode = true
cmd = 'C:/Program Files/SourceGear/Common/DiffMerge/sgdm.exe' -merge -result=\"$MERGED\" \"$LOCAL\" \"$BASE\" \"$REMOTE\"

### git client命令

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
- git rebase 合并commit
- git stash保存本地修改
- git reset 放弃本地修改还原历史版本
- git checkout 导出指定版本
