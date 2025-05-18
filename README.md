# GitTest
最近在大公司发现项目管理跟小公司确实不一样，必须得重新脑补一下相关的git命令，基于git的代码管理平台有， github, gitlab, gitee, gerrit.

---
# gerrit
最近公司的代码管理工具，使用了gerrit, 第一次使用gerrit，踩了很多坑。大公司的管理制度跟小公司确实不一样，必须精确到每一笔提交，后续出了问题
，都能精确到是哪一笔提交。gerrit提供了代码审查工具， 每一笔提交领导都会对代码进行review. 包括提交的commit message都有固定的模板， 包括各种各样的
lint 规则检查。 刚进公司对gerrit 有一些不明白， 今天特意脑补一下git的各种各样的命令。

---
# git的相关命令

1. `git init`</br>
   (在项目的根目录下面执行，初始化git仓库)
2. `git config —global user.name ‘richzjc’`
   </br>
   `git config —global user.email ‘zhangjianchuan@huaqin.com’`
   </br>
   代码提交到远程需要查看代码是谁提交的， 因此需要配置用户名和邮箱
4. `git config —list`</br>
   查看git的配置，包括user.name, user.email
5. `git add .` </br> 将文件添加到暂存区
6. `git remote add origin url` </br>关联远程的仓库地址
7. `git fetch` </br>获取远程的branch 和 tag
8. `git branch` </br> 查看所有的本地分支
9. `git branch -a` </br> 查看所有本地与远程的所有分支
10. `git tag v1.0.0` </br> 创建本地tag
11. `git tag` </br> 查看本地所有的tag
12. `git push --tags` </br> 将所有本地tags推送到远端
13. `git checkout tag名或者分支名` </br> 切换到指定的tag或者分支名
14. `git checkout -b masterNew master` </br>从给定的master切换出一个新的分支 masterNew
15. `git commit -m '提交的备注信息'` </br> 将暂存区里面的文件内容提交到本地分支
16. `git push -u origin master` </br> 将代码推送到远程的master
17. `git branch --set-upstream-to=origin/main master` </br> 将本地的master分支与远程的main分支关联
18. `git rm --cached  文件路径` </br> 从暂存区移除文件， 文件回到了工作区
19. `git rm -f 文件路径` </br> 从暂存区移除文件， 并删除工作区里面的文件
20. `git restore 文件路径` </br> 将工作区里面的文件还原成暂存区的文件内容， 会丢弃工作区的内容修改
21.  

