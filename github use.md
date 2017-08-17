* 如何创建文件夹    
  在网页上点击新建文件，在命名框中添加`/`就变成文件夹

* 远程仓库
  - 添加
`$git remote add [name] [url]`
  - 删除
`$git remote rm [name]`

* 分支
  - 删除远程分支
`$git push origin --delete <remoteBranchName>`
  - 推送本地分支
`$git push <remoteRepository> <localBranchName>`
  - 合并其他分支到当前分支
`$git merge <branchName>(要合并的分支)`
