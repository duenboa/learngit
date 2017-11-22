


https://git.oschina.net/duenboa/boa-gitstu


一. babun通过ssh直接访问远程机器

>> ssh mac@192.168.0.224  
>> yes/no? yes
>> password:  回车

//-------------------------------- 基础配置 --------------------------------
二. git配置 : git config
级别: --local 当前项目, --system 系统级别(所有用户), --global用户级别(当前用户)

// git 配置 alias
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.br branch
git config --global alias.unstage 'reset HEAD'
git config --global alias.last 'log -1'
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"


//----------------------------- 克隆代码 clone ---------------------------------------
//配置ssh key公钥.
> ssh-keygen -t rsa -C 'duenboa@163.com' 
说明:  调用系统ssh命令生成公钥对, 完成后在用户目录下/.ssh/会有三个文件:  id_rsa  id_rsa.pub  known_hosts
1. 打开id_rsa.pub文件: 
> cat id_rsa.pub
2. 进入github用户管理页面, settings, 公钥管理, 新增, 将id_rsa.pub文件的内容拷贝进去即可. 

//克隆远程分支
git clone url.git 分支名

//添加文件到缓存区
git add file1 file2 file3

//当前工作区与缓冲区比较
git diff --cached

//当前工作区与发生改动的文件的比较( 最新一次commit后的状态与工作区(发生修改,没有add的文件), 最新一次commit后台状态与缓冲区(发生add, 未commit的文件) )
git status

//提交
git commit -m ' Boa commit . # add file : 1.html'



//------------------------------------- 分支 branch, checkout ---------------------------------------
//新建分支
git branch dev_20170820

//切换分支(有则切换, 没有则新建分支)
git checkout -b dev_2.170822

//本地分支列表
git branch

//远程分支列表
git branch --remote 

//所有分支列表
git branch -a 

//删除分支
git branch -d dev_20170820


//----------------------------------- 提交代码 add, commit, push ----------------------------
//添加改动文件到缓存区
dev_20170101> git add .

//提交
dev_20170101> git commit -m "fixed conflicts"

//将远程的master分支更新下来. (如果是基于远程仓库的dev分支开发, 则: git pull origin dev)
dev_20170101> git pull origin master

//合并主干代码到当前分支(当前处在分支)
dev_20170101> git merge --no-ff master

//要将代码推送到远程主干. (如果需要将dev分支代码推送到远程dev分支, 则: git push origin dev)
> git push origin master



//------------------------------------- 标签 tag ----------------------------------------
//在当前分支打标签(add)
git tag -a dev_20170808 -m “备注:开发版本dev_20170808”

//在当前分支删除指定标签(del)
git tag -d dev_20170808

//给指定commit打标签(通过 git log 获取commit的id)
git tag -a reg_20170808_01 9fbc3d0

//查看当前分支下的所有标签
git tag

//指向标签所在的代码状态
git checkout dev_20170808_01

//# 将v0.1.2标签提交到git服务器
git push origin v0.1.2 

//# 将本地所有标签一次性提交到git服务器
git push origin –tags 

// 查看标签的版本信息
git show dev_20180101













