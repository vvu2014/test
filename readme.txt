echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/vvu2014/test.git
git push -u origin master

git branch

git revert  test


git reset  test


git branch1  test

git checkout commitid -b branchname



***********************
**
对工作区中文件的修改分为三种情况：

（1）修改，但没有用git add将修改添加到暂存区；

（2）修改，已经使用git add将修改添加到暂存区；

（3）修改，已经使用git add将修改添加到暂存区，并再次进行修改。

对于第一种情况，直接使用git checkout -- 文件，即可撤销修改，撤销修改就回到和版本库一模一样的样子。

第二种情况，先使用git reset HEAD -- 文件，然后在使用git checkout -- 文件进行修改撤销。

第三种情况 先使用git checkout -- 文件，文件就会变成添加到暂存区后的状态，也就转换成了“第二种情况”，然后，在使用情况（2）中的处理方法，即可将文件恢复到与版本库一致的状态。

总之，记住一点：“git checkout -- 文件”命令，撤销的是工作中文件的修改，而“git reset HEAD -- 文件”命令，撤销的是暂存区中文件的修改。

*************************


******************************************
******************************************
commit id从0开始计算
// 回退到上一个commit版本, HEAD严格来说不是指向提交，而是指向master，master才是指向提交的，所以，HEAD指向的就是当前分支。
$ git reset --hard HEAD^
HEAD is now at ea34578 add distributed

git reset --hard 3628164回退到某个版本

git reflog用来记录你的每一次命令

提交后，用git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别

git branch命令会列出所有分支，当前分支前面会标一个*号

git log --graph --pretty=oneline --abbrev-commit 分支合并查看

git merge --no-ff -m "" branch-name 参数就可以用普通模式合并,并后的历史有分支，能看出来曾经做过合并,而fast forward看不出
git tag <tag name>		在某分支打标签， git tag也可以查看所有标签
git show <tagname>or<commit id>	查看标签信息，标签是按字母顺序， git show可以查看某个commitid对应的修改记录
如果要推送某个标签到远程，使用命令git push origin <tagname>
git check-ignore 查看到底哪个规则写错，git check-ignore -v App.class，App.class本来是要add，但是比配了忽略文件

git-revert - Revert some existing commits。如果使用默认的注释，可以在命令中加上--no-edit参数
git revert 是生成一个新的提交来撤销某次提交，此次提交之前的commit都会被保留，
git revert HEAD~0是撤销最新的commit，不会有冲突，但是HEAD~1以后的可能会有冲突


git-reset - Reset current HEAD to the specified state。
git reset：1. 文件从暂存区回退到工作区 2. 版本回退 
git reset HEAD filename ：回退文件（不能使用--soft），将文件从暂存区回退到工作区　　　
soft 参数：git reset --soft HEAD～1 意为将版本库软回退1个版本，所谓软回退表示将本地版本库的头指针全部重置到指定版本，且将这次提交之后的所有变更都移动到暂存区

默认的mixed参数： git reset HEAD～1 意为将版本库回退1个版本，将本地版本库的头指针全部重置到指定版本，且会重置暂存区，即这次提交之后的所有变更都移动到未暂存阶段

hard参数：git reset --hard HEAD～1 意为将版本库回退1个版本，但是不仅仅是将本地版本库的头指针全部重置到指定版本，也会重置暂存区，并且会将工作区代码也回退到这个版本 

git remote命令列出所有远程主机 ,使用-v选项，可以参看远程主机的网址。
git remote show <主机名>

git checkcout -b branchname 在当前分支创建并切换到新分支
git checkcout commitid -b branchname 在当前分支的某个历史提交点基础上创建并切换到新分支
git merge branchname合并分支到当前分支
git push origin branchname合并分支到当前分支， 在分支下提交代码到远程仓库，不能只Git push，要指定远程分支名称
git log --graph --pretty=oneline --abbrev-commit 查看分支合并情况

git tag -a v0.1 -m "version 0.1 released" 3628164 带有说明的标签，用-a指定标签名，-m指定说明文字
git show <tagname> 可以看到说明文字，默认标签是打在最新提交的commit上的
git push origin <tagname> 推送某个标签到远程， 打标签的时候自动标注该标签为release版本
git push origin --tags 一次性推送全部尚未推送到远程的本地标签
******************************************

git branch2 test
