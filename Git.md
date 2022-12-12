# Git

## Github账号密码
fanxf@yisa.com  Gitforfanxf002
xuefengfan@163.com  GitForfanxf003
1163132297@qq.com   GitForFanxf001
pass:fxf9.....9

## 工作机制：
### 集中式：
​		代码放在服务器，所有人修改同一套代码，存在单点故障风险。
### 分布式：
​		每个人都在自己的电脑上做版本控制，从远程库拉取、修改、然后再推送远程库
​		使用步骤：在工程所在的文件夹打开git bash 添加暂存区--提交本地库--推送远程库
Git分类：
​	GitLab：基于局域网的代码托管中心
​	GitHub：外网
​	Gitee:国内网站
​	安装：默认用vim编辑器，检查Windows和linux并自动转换换行符
### 常用命令：
​	设置用户签名：git config --global user.name 用户名
​	设置用户签名：git config --global user.email 用户名
​	初始化本地库：git init 
​	查看本地库状态：git status
​	添加暂存区：git add 文件名
​	提交本地库：git commit -m "日志信息" 文件名
​	查看历史记录：git reflog
​	版本穿梭：git reset --hard 版本号

### Git分支：

​	创建分支，然后再其他分支上开发不影响主分支的运行，等开发好以后再合并
​	常用命令：
​	创建分支：git branch 分支名
​	查看分支：git branch -v
​	切换分支：git checkout 分支名
​	将制定分支合并到当前分支：git merge 分支名

### Git团队协作：
​	团队内合作：邀请成员，管理员推送代码，拉去代码，其他人克隆代码，修改代码，推送代码。在本地库和远程库之间：推送，拉去，克隆
​	团队间合作：团队A要求团队B帮忙写代码：B从A的远程库中fork代码，然后克隆修改再推到自己的远程库，然后再给A发送一个拉取请求，
​		A审核代码以后，可以合并到自己远程库的分支中，然后又可以从远程库中拉取代码到本地库

	常用命令：
	查看当前所有远程库别名：git remote -v 
	给远程库起别名：git remote 别名 分支名
	将本地分支推送到远程仓库：git push 别名 分支
	克隆远程仓库的内容：git clone 远程地址
	拉取远程库的分支并且合并到本地分支：git pull 远程库地址别名 远程分支名
	邀请成员步骤：settings-manage access-invite a collaborator

### 协作规范：各个分支是干嘛的？
初始化-main分支-develop分支（不允许直接开发）-fork到自己的远程仓库--feature-功能名-1--自测--推到远程仓库--发起pull request请求--合并到本地分支--发起集成测试--完成之后--合并到main分支--
交公司测试--有问题后hot-fix分支修改--打包发布。