git workflow测试


# 新建一个仓库

- 在github上添加一个项目并提交
- `git init`
- `git add *`
- `git commit -m "first commit"`
- `git remote add origin https://github.com/youngqqcn/GitWorkFlowTest.git`
- `git remote -v`
- `git push -u origin master`


# 查看提交历史记录

`git log`


# 打标签

附注标签

`git tag -a v0.0.1 -m "备注信息"`


轻量标签

`git tag v0.0.2 -lw`

后期打标签(补上)

`git tag -a v1.2 9fceb02`


推送标签

推送指定标签: `git push origin v1.5`

一次性推送多个标签:`git push origin --tags`



删除标签

`git tag -d v0.0.1`

删除本地标签后,更新远程仓库的标签: `git push origin --delete v0.0.1`

