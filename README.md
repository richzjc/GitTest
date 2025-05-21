# 吐槽
请原谅我很菜， 以前只知道使用一些git的基本命令，真正遇到了问题真的是无从下手， 趁最近有时间，脑补了一下git. 
在我看来，要想了解git,首先的明白： 工作区， 暂存区， 本地仓库，远程仓库， 指针。需要理解每一个命令具体影响的是哪一块区域。


# GitTest
最近在大公司发现项目管理跟小公司确实不一样，必须得重新脑补一下相关的git命令，基于git的代码管理平台有， github, gitlab, gitee, gerrit。 
个人觉得，要想真正的了解git的原理， 就得了解一下.git目录下面每一个文件的作用。正常的话， 了解一下上层的命令是如何使用就够了。

---
# gerrit
最近公司的代码管理工具，使用了gerrit, 第一次使用gerrit，踩了很多坑。大公司的管理制度跟小公司确实不一样，必须精确到每一笔提交，后续出了问题
，都能精确到是哪一笔提交。gerrit提供了代码审查工具， 每一笔提交领导都会对代码进行review. 包括提交的commit message都有固定的模板， 包括各种各样的
lint 规则检查。 刚进公司对gerrit 有一些不明白， 今天特意脑补一下git的各种各样的命令。

---
# git的相关命令
`git init`</br>
   (在项目的根目录下面执行，初始化git仓库)
   ---
`git config —global user.name ‘richzjc’`
   </br>
`git config —global user.email ‘zhangjianchuan@huaqin.com’`
   </br>
   代码提交到远程需要查看代码是谁提交的， 因此需要配置用户名和邮箱
`git config —list`</br>
   查看git的配置，包括user.name, user.email
`git add .` </br> 将文件添加到暂存区
`git remote add origin url` </br>关联远程的仓库地址
`git fetch` </br>获取远程的branch 和 tag
`git branch` </br> 查看所有的本地分支
`git branch -a` </br> 查看所有本地与远程的所有分支
`git tag v1.0.0` </br> 创建本地tag
`git tag` </br> 查看本地所有的tag
`git push --tags` </br> 将所有本地tags推送到远端
`git checkout tag名或者分支名` </br> 切换到指定的tag或者分支名
`git checkout -b masterNew master` </br>从给定的master切换出一个新的分支 masterNew
`git commit -m '提交的备注信息'` </br> 将暂存区里面的文件内容提交到本地分支
`git push -u origin master` </br> 将代码推送到远程的master
`git branch --set-upstream-to=origin/main master` </br> 将本地的master分支与远程的main分支关联
`git rm --cached  文件路径` </br> 从暂存区移除文件， 文件回到了工作区
`git rm -f 文件路径` </br> 从暂存区移除文件， 并删除工作区里面的文件
`git restore 文件路径` </br> 将工作区里面的文件还原成暂存区的文件内容， 会丢弃工作区的内容修改
`git switch 分支名` </br> 用于切换到指定分支， git checkout 分支名，也可以切换分支名， 这两者有啥区别， 知道吗？
`git reset 模式  提交的hash值` </br>
       --hard:</br> 该操作会替换，暂存区， 工作区， 本地仓库的文件修改
    --soft: </br> 替换本地仓库的文件内容
     --mixed: 替换本地仓库与 暂存区的文件内容。 自己操作一遍就知道结果了
git it log / git log --all </br> 查看提交的日志记录
git merge 分支名 </br> 在没有冲突的情况下，会自动提交到本地仓库， 影响工作区， 暂存区， 本地仓库
git merge --no-commit 分支名 </br> 如何只想内容同步到工作区， 添加--no-commit参数
git merge --abort </br> 放弃上一次的merge操作， 恢复工作区， 暂存区， 本地仓库的文件
git stash  /   git stash pop </br>
    主要应用于在当前分支的工作区和暂存区有修改，  但是不想急着提交到本地仓库， 可以调用 git stash先缓存，在切换分析， 恢复工作区 修改则调用 git stash pop
git commit --amend </br> 这个命令，主要想说一下--amend的用法，我发现我公司在使用gerrit进行代码管理的时候， --amend的参数很重要。主要用于对上一次提交进行修改
git cherry-pic 提交的哈希值 </br> 将某一笔提交应用到当前分支， 并应用到了本地仓库
git cherry-pic -n 提交的哈希值 </br> 将某一笔提交应用到当前分支， 并应用到了工作区

