# git 迁移远程仓库

## 什么是迁移git远程仓库 ？

当项目需要在 GitHub/GitLab 间迁切换，或从一个 GitHub 账号改到另一个 GitHub 账号时，又不希望丢失原本 commit 的 log 记录时，需要用到远程仓库迁移。

## 操作

### 查看项目当前远程放仓库 remote url

``` bash
$ git remote -v
origin  git@github.com:SikyChen/sourceProject.git (fetch)   # 返回项目当前远程仓库地址
origin  git@github.com:SikyChen/sourceProject.git (push)
```

### 使用 git remote set-url 命令切换远程仓库地址

``` bash
$ git remote set-url origin git@github.com:SikyChen/targetProject.git
```

### 确认切换成功

``` bash
$ git remote -v
origin  git@github.com:SikyChen/targetProject.git (fetch)   # 返回项目当前远程仓库地址
origin  git@github.com:SikyChen/targetProject.git (push)
```

### 提交代码到新仓库

``` bash
$ git push origin master        # 若有多条分支，需要每条分支push一次
$ git push -f origin master     # 使用 -f 参数，可强行推送
```

#### 强行推送报错

如果该新项目不是第一次 push 代码，则有可能报如下错误：

``` bash
[remote rejected] master -> master (pre-receive hook declined)
```

这是因为 GitHub/GitLab 的 master 分支是受保护的，需要解除保护后再 push ：在项目设置中的 Protected Branches 下，将 master 设置 Unprotect 就好了。