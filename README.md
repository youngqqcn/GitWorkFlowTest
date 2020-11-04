# Git常用命令


> 参考文档: https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%9A%84%E6%96%B0%E5%BB%BA%E4%B8%8E%E5%90%88%E5%B9%B6
git workflow测试


### 新建一个仓库

- 在github上添加一个项目并提交
- `git init`
- `git add *`
- `git commit -m "first commit"`
- `git remote add origin https://github.com/youngqqcn/GitWorkFlowTest.git`
- `git remote -v`
- `git push -u origin master`


### 查看提交历史记录

`git log`


### 打标签

- 附注标签 : `git tag -a v0.0.1 -m "备注信息"`


- 轻量标签: `git tag v0.0.2 -lw`

- 后期打标签(补上) : `git tag -a v1.2 9fceb02`

- 推送标签
  - 推送指定标签: `git push origin v1.5`
  - 一次性推送多个标签:`git push origin --tags`

- 删除标签 : `git tag -d v0.0.1`
- 删除本地标签后,更新远程仓库的标签: `git push origin --delete v0.0.1`

- 检出标签: `git checkout 2.0.0`


### 分支

- 创建分支: `git branch branch_doc`
- HEAD指针:是当前所在分支的别名
- 切换分支: `git checkout branch_doc`



让我们来看一个简单的分支新建与分支合并的例子，实际工作中你可能会用到类似的工作流。 你将经历如下步骤：

- 1.开发某个网站。
- 2.为实现某个新的用户需求，创建一个分支。
- 3.在这个分支上开展工作。

正在此时，你突然接到一个电话说有个很严重的问题需要紧急修补。 你将按照如下方式来处理：

- 1.切换到你的线上分支（production branch）。
- 2.为这个紧急任务新建一个分支，并在其中修复它。
- 3.在测试通过之后，切换回线上分支，然后合并这个修补分支，最后将改动推送到线上分支。
- 4.切换回你最初工作的分支上，继续工作。

参考:
> https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E8%B4%AE%E8%97%8F%E4%B8%8E%E6%B8%85%E7%90%86#_git_stashing


在切换分之前, 如果还有没提交的修改, 有两种选择: 1.提交修改 , 2.如果暂时还不想提交,则使用 `git stash`命令将修改隐藏起来

使用`git stash apply --index`


### 分支工作流程:

- 新建分支: `git checkout -b  fixissue23`  或者 `git branch fixissue23` , `git checkout fixissue23`

- 分支合并: `git checkout master` , `git merge fixissue23`


- 解决冲突: 如果分支合并过程中遇到冲突, 则需要解决冲突,再提交


### 分支管理

`git branch` 查看所有分支
`git branch --merged` 查看已经合并的
`git branch --no-merged` 查看尚未合并的分支
`git branch --no-merged master` 查看尚未合并到master分支的有哪些


参考文档:
> https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E5%BC%80%E5%8F%91%E5%B7%A5%E4%BD%9C%E6%B5%81

### 分支开发工作流

- 长期分支:
  - master : 稳定版本
  - dev: 开发
  - topic

- 主题分支:
  比如, 开发一个新的功能时, 建立一个分支, 开发完成之后, 测试通过之后, 可以合并主分支


- 远程分支:
  - `git fetch`: 只是拉取数据, 不会自动合并
  - `git pull`: 拉取数据, 然后自动合并




