# Git 同步 fork 拉取远程仓库代码

如果我们 fork 了别人的代码，原作者改动了，自己的 github 想要同步到最新版，怎么办

1. 打开本地仓库 git
2. 把想要同步的这个仓库关联到本地 upstream
   ```bash
    git remote add upstream https://github.com/*******.git
   ```
3. 查看状态是否配置成功
   ```bash
    remote -v
   ```
4. 拉取仓库下所有分支
   ```bash
     git fetch upsteam
   ```
5. 把上游的远程代码合并到本地的 master 分支
   ```bash
     git merge upstream/master
   ```
6. 现在你本地的 master 就同步到最新版本了
