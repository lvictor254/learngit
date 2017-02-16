learngit
git init   #将目录变成Git可以管理的仓库
git add file #将file添加进入缓存中
git commit   # 将所有缓存中的文件加入库中 git commit -m "title" 参数-m 后面加入说明
git status  #命令查看结果 可以掌握仓库的当前状态
git diff file   #查看未加入缓存，工作区中文件的修改状态
git log   #查看历史记录  git log --preety=oneline
git reset --hard commit_id #版本回退 HEAD^ HEAD^^ 或者将缓存区修改退回到工作区
git reflog   #命令历史记录
git checkout -- file   #丢弃工作区修改
git rm file    #从版本库中删除file
git remote add origin git@github.com:lvictor254/learngit.git #关联本地与远程代码库 
git push -u origin master  #由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令

git push origin master  #推送命令
git clone git@github.com:lvictor254/gitskills.git  #克隆一个本地库
git checkout -b dev  #git checkout命令加上-b参数表示创建并切换，相当于以下两条命令
git branch dev
git checkout dev
Switched to branch 'dev'
git branch  #查看当前分支  *dev  master  有*表示当前分支
git checkout master  #切换回master分支
git merge dev  #git merge命令用于合并指定分支到当前分支
git branch -d dev   #删除dev分支
git log --graph  #看到分支合并图 git log --graph --pretty=oneline --abbrev-commit
git merge --no-ff -m "merge with no-ff" dev  #--no-ff参数，表示禁用Fast forward 强制禁用Fast forward模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息 (因为本次合并要创建一个新的commit，所以加上-m参数，把commit描述写进去)
git stash   #可以把当前工作现场“储藏”起来
git stash list   #查看保存的工作现场
git stash apply  #恢复工作现场  此时仍然需要git stash drop 删除stash
git stash pop    #恢复工作现场，此时自动删除stash
git stash apply stash@{0}   #恢复制定工作现场
git branch -D file   #强制删除分支
git remote  #查看远程库信息  -v 显示更详细信息
git checkout -b branch-name origin/branch-name   #在本地创建和远程分支对应的分支
git branch --set-upstream branch-name origin/branch-name  #建立本地分支和远程分支的关联
git pull  #从远程抓取分支
git tag v1.0  #默认标签是打在最新提交的commit上的
git tag v0.9 commit_id  #git log --pretty=oneline --abbrev-commit列出仓库中版本，对commit_id打上标签
git show commit_id   #查看标签信息
git tag -a v0.1 -m "version 0.1 released" 3628164(commit_id)  #创建带有说明的标签，用-a指定标签名，-m指定说明文字

git tag -s v0.2 -m "signed version 0.2 released" fec145a  #-s用私钥签名一个标签
git tag -d v0.1   #删除标签
git push origin v1.0   #推送某个标签到远程
git push origin --tags   #一次性推送全部尚未推送到远程的本地标签
git push origin :refs/tags/v0.9   #删除远程标签，首先删除本地标签
