# Questions-about-Git
Learning Git by asking questions


#### 如何设置本机的 Git 用户名和邮件 ？
`git config --global user.name "<用户名>"`

`git config --global user.email "<电子邮件>"`

以下命令能让Git以彩色显示。

`git config --global color.ui auto`

#### 常见的 Git 基础命令 ？
使用status命令确认工作树和索引的状态。

`git status`

在本地新建 Repo

`git init`

#### 进行了修改已经 `commit`，你再 `pull` 有冲突，如何解决冲突 ？
分几种情况讨论：
1. 多成员修改不同文件，或多成员修改不用文件的不同区域，或同时修改文件名和文件内容

    `git pull`

      简而言之，`git pull`可以自动进行 merge，解决很多问题
2. 同时修改某一行代码

    `git pull`
    
    自动 merge 不用解决所有问题，对于自动 merge 解决不了的问题，需要手动解决


#### 进行了修改还未 `commit`，你再 `pull` 有冲突，如何解决冲突 ？
分两种情况考虑：
1. 如果你希望保留已经做的修改
    ```
    git stash
    git pull origin master
    git stash pop stash@{0}
    ```
    然后使用 `git diff -w 文件名` 来查看代码自动合并的情况
    
 2. 如果你希望云端代码覆盖本机
    ```
    git reset --hard
    git pull
    ```
