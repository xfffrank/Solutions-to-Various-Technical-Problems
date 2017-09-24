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

* 在 Github 上添加公钥         
1.`$ ssh -T git@github.com`检查权限  
  `Permission denied (publickey).`    
2.生成 ssh 密钥         
```
$ ssh-keygen -t rsa -C "xfffrank"
Generating public/private rsa key pair.
Enter file in which to save the key (/home/FrankXie/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/FrankXie/.ssh/id_rsa.
Your public key has been saved in /home/FrankXie/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:ae01V2/IEOMh12ZXKSaL33Ro1cBmvHMcq0fuoQ12o+0 xfffrank
The key's randomart image is:
+---[RSA 2048]----+
|          . =+..=|
|           = *O+o|
|          . *=+++|
|         + . *o*+|
|        S o * Ooo|
|       . . o B B |
|          . . X o|
|             o + |
|              .E |
+----[SHA256]-----+

```

3.复制公钥   


