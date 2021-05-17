---
title: 清空github仓库而不是删除重新创建
date: 2021-05-17 12:30:07
tags:
---

## 清空github仓库而不是删除重新创建
```
rm -rf .git
git init
git add .
git commit -m "Initial commit"
git remote add origin git@github.com:<YOUR ACCOUNT>/<YOUR REPOS>.git
git push -u --force origin master
```
如果是main的branch
```
rm -rf .git
git init
git add .
git branch -M main
git commit -m "Initial commit"
git remote add origin git@github.com:<YOUR ACCOUNT>/<YOUR REPOS>.git
git push -u --force origin main
```
