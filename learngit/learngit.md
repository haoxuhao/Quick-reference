本地仓库常用命令

	* git init  //init a repository
	* git add <file> <file> ...      //可同时添加多个文件；文件需要添加后缀；可以是文件夹，如果是文件目录则将文件目录下的所有文件添加
	* git commit -m "message" //提交所有add进暂存区的文件的修改到版本库，message为本次提交的提示信息
	* git status                          //查看当前仓库的状态
	* git diff <file>                    //查看修改的内容，file 为需要查看的文件修改，如果不添加文件file，则所有文件的更改都会显示出来
	* git log --pretty=oneline                          //查看提交日志，添加后缀--pretty=oneline 只显示版本号和提示信息
	* git reset --hard HEAD^                   //回退到上一个版本，HEAD^^上上个版本，HEAD~100回退到上100个版本
	* git reset --hard commit id               //commit id 为版本的id号；可以在窗口内向上查找，或者使用git reflog 查看分支管理id号
	* git diff HEAD -- <file>                    //查看被修改但是没有被提交的修改
	* git checkout -- <file>                    //撤销当前工作区内文件的修改，回到上一次commit或add的状态，具有一键还原的功能，但只能回到上一次
	* git reset HEAD <file>                     //将当前版本回退到工作区
	* git rm <file>                                  //删除工作区的文件

远程仓库使用的命令

	* git remote add origin git@github.com:GitHubId/learngit.git    //GitHubId是github的仓库根目录，用于同步本地仓库到远程主机

	* git push -u origin master                                                    //将本地仓库上传到远程主机上，-u命令在第一次关联时加

分支创建与合并

	* git branch                                    //查看当前分支
	* git checkout  branchname             //切换分支到branchname
	* git checkout -b branchname          //创建+切换到branchname
	* git merge branchname                  //合并分支到当前分支
	* git branch -d branchname             //删除分支branchname

当前分支状态管理

	* git stash                                       //保存当前分支的工作状态
	* git stash pop                               //回复现场
	
git分支管理学习的很好的一个网站

	https://learngitbranching.js.org/
