---
title: Github
date: 2020-12-28 00:00:00
categories: 
  - frontEnd
tags: 
  - git
permalink: /pages/ae50e9/
---
# 获取公钥
```bash
ssh-keygen -t rsa -b 4096 -C 你的邮箱
cat ~/.ssh/id_rsa.pub                           # 得到公钥内容
ssh -T git@github.com
git remote add origin git@xxxxxxx
git push -u origin master
```
# 高级操作
```bash
touch ~/.bashrc
echo 'alias ga="git add"'>> ~/.bashrc
echo 'alias gc="git commit -v"'>> ~/.bashrc
echo 'alias gl="git pull"'>> ~/.bashrc
echo 'alias gp="git push"'>> ~/.bashrc
echo 'alias gco="git checkout"'>> ~/.bashrc
echo 'alias gst="git status -sb"'>> ~/.bashrc
```
最后 code ~/.bashrc 在文件最后加上
`alias glog="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit -- | less"
`
# 上传代码
1. 新建GitHub Repo， 复制其ssh地址
2. git remote add origin git@xxxxxx
3. 在本地添加远程仓库地址
4. origin是远程仓库的默认名字， 可以换， 建议不要换
5. 不要使用https：//地址，因为每次都需要密码
6. `git push-u origin master`
7. 推送本地master分支到远程origin的master分支
8. 你就git pull一下
9. git pull是先把远程分支合并到本地对应的分支
10. 如果远程分支没有更新过， 才可以省略
11. git pull-u origin master的意思是设置上游分支之后就不用再设置上游分支了， 直接git pull； git push；

## 如何上传其他分支


方法一
git push origin x：x
方法二
git checkout x
git push-u origin x

## 通灵术


git stash/git stash pop
你不想提交代码，又不想删除代码
那么就可以找个空间把代码临时藏起来

## 改变git提交方式
[![PaRXP.png](https://ss.im5i.com/2021/08/12/PaRXP.png)](https://cloudimge.com/image/PaRXP)