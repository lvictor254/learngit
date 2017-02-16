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
