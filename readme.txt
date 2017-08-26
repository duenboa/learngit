


https://git.oschina.net/duenboa/boa-gitstu


一. babun通过ssh直接访问远程机器

>> ssh mac@192.168.0.224  
>> yes/no? yes
>> password:  回车


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


//克隆远程分支
git clone url.git 分支名

//添加文件到缓存区
git add file1 file2 file3

//
git diff --cached

//
git status

//提交
git commit -m 'do sth. 
	a
	detials: 
	1. 
	2.'


//新建分支
git branch dev_20170820

//本地分支列表
git branch

//远程分支列表
git branch --remote 

//所有分支列表
git branch -a 

//删除分支
git branch -d dev_20170820


//将远程的master分支更新下来. (如果是基于远程仓库的dev分支开发, 则: git pull origin dev)
git pull origin master

//添加改动文件到缓存区
git add .

//提交
git commit -m "fixed conflicts"

//要将代码推送到远程主干. (如果需要将dev分支代码推送到远程dev分支, 则: git push origin dev)
git push origin master




