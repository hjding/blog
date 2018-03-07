#git高层命令porcelain
[TOC]

##协议
###ssh
1. 生成ssh秘钥
		ssh-keygen -t rsa
	![](./img/1_ssh-keygen.PNG)
2. 将~/.ssh/id_rsa.pub公钥添加至个人远端
		http://rnd-isourceb.huawei.com/profile/keys -> add SSH Key
    ![](./img/2_id_rsa.pub.PNG)
    ![](./img/3_add ssh keys.PNG)
3. 测试ssh通信
		ssh -T git@rnd-isourceb.huawei.com
	![](./img/4_ssh-T.PNG)
##git高层命令的简单实用
###1.新建本地分支并切换
1. 新建本地分支并切换
		git checkout -b test
	![](./img/5_git checkout -b.PNG)
	等同于
    	git branch -f test
        git checkout test
    ![](./img/5_git branch -f_git checkout.PNG)

###2.更新本地代码到远端(push)
1. 查看当前本地版本库**状态**
		git status
	![](./img/6_git status-clean.PNG)
2. 将**工作区**所有修改添加到**暂存区**
		git add .
	![](./img/7_git add.PNG)
	![](./img/6_git status-not staged.PNG)
3. 将暂存区提交到**本地版本库**
		git commit
	![](./img/8_git commit.PNG)
	![](./img/6_git status-to be commited.PNG)
4. 将本地版本库推送到**个人远端库**
		git push origin_hjd test:test
	![](./img/9_git push.PNG)
5. 从个人远端库到**中心远端库**发起**MR**(merge request)
		http://rnd-isourceb.huawei.com/hWX353647/DVB_CODE/merge_requests/new
	![](./img/10_git mr.PNG)

###3.将远端代码更新到本地(pull = fetch + mrege)
1. 将远端代码更新到本地
		git pull origin master
	![](./img/11_git pull.PNG)
	等同于
    	git fetch origin
        git merge origin/next
	![](./img/11_git fetch_git merge.PNG)

##参考资料

