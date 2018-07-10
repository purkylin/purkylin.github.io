---
title: git需要经常查阅的命令
date: 2018-07-10 11:12:44
tags: git
---

1. Amend
```bash
git commit --amend -a -m "Fix last commit"
```
2. Config
```bash
git config [--global] user.[name|email]
```
3. Remote
```bash
git remote -v` 
git remote add origin Git_Repository_URL
```
4. Modify last commit username or email
```bash
git commit --amend --author="Purkylin <purkylin@gmail.com>"
```
