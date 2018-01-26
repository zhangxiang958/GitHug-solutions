# The Solutions of Githug

## 1. init
```
git init
```
可以使用 git init 来初始化一个本地 git 仓库.
## 2. config
```
git config --local user.name shawncheung
git config --local user.email shawncheung702@gmail.com
```
使用 git config 来配置你的个人信息, 我使用 --local 是因为为了不让 githug 的信息影响了我的 git 日常使用, 决定本地配置, 当然你也可以使用 ---global 参数.
## 3. add
```
git add README
```
本关需要将 README 文件使用 git add 命令添加索引 
## 4. commit
```
git commit -m "commit message"
```
使用 git commit 命令将文件的修改提交到缓存区
## 5. clone
```
git clone https://github.com/Gazler/cloneme
```
通过 git clone 命令, 指定一个远程仓库 url, 克隆远程仓库.
## 6. clone to folder
```
git clone https://github.com/Gazler/cloneme my_cloned_repo
```
具体可以使用 git clone -h 来查看, git clone url path 中的 path 选项可以指定远程仓库下载到本地指定文件夹下, 也就是可以指定路径.
## 7. .gitignore
```
nano .gitignore
```
使用自己熟悉的文本编辑器来编辑 .gitignore 文件(这里用的是 nano), 这个 .gitignore 文件会记录下在提交时需要被忽略的文件进而避免不必要的文件提交到远程仓库.
githug 中要求忽略所有 .swp 后缀的文件, 所以可以这样写:
```
.gitignore
*.swp
```
## 8. .gitignore includes
```
nano .gitignore
```
和上一关一样, 需要编辑 .gitignore 文件, 本关的要求是忽略所有 .a 后缀的文件, 但是 **lib.a** 除外, 所以 .gitignore 可以这么写:
```
*.a
!lib.a
```
上面 ! 的意思就是不包括.
## 9. status
```
git status
```
这个是非常常用的命令, 用于查看目前 git 缓存区与工作区的状态, 经常在 git add 之前使用.本关要求查看未跟踪的文件名, 使用 git status 命令可以看到红色文件名的就是未跟踪的.
所以本关答案是 database.yml.
## 10. Number_of_files_committed
```
git status
```
和上一关一样, 同样使用 git status 来查看文件的状态, 本关要求查看有多少个文件被修改了, 使用 git status 可以查看红色文件名的, 并且在前列有提示 changed not stage for commit.
本关答案为 rubyfile5.rb.
## 11. rm
```
git status
git add deleteme.rb
git commit -m "delete deleteme.rb"
```
在硬盘中删除了一个文件, 但是在 git 仓库中并没有删除掉, 可以使用 git add, git commit 来确实提交这个更改.在此之前需要用 git status 来查看到底删除了哪个文件, 本关是 **deleteme.rb**.
## 12. rm cached
```
git rm deleteme.rb
```
这个场景很常见, 例如你不小心添加了某个你并不想添加到缓存区的文件, 所以需要将添加的记录删除, 但是不会将硬盘上的文件删除, 可以理解为一个简单版的 git reset.
## 13. stash
```
git stash
```
将目前工作区的更改暂存起来, git 维护一个栈来记录临时保存的更改, 当使用 git stash 时, 文件将回到上一个 commit 的状态, 当你需要再次用到刚暂存的更改的时候, 可以 git stash pop{idx}
来恢复, 常用于在 push 代码前暂存代码将部分更改提交.
## 14. rename
```
git mv oldfile.txt newfile.txt
```
本关可以将 oldfile.txt 更改名字为 newfile.txt, 但是前提是 oldfile.txt 要先被 git 跟踪.
## 15. restructure
```
mkdir src
git mv *.html src
```
本关要求将所有 .html 后缀的文件移到 src 文件夹下, 首先需要使用 mkdir 命令创建一个文件夹, 然后使用 git mv 命令通过通配正则 *.html 将所有的 html 文件移到 src 文件夹下.
## 16. log
```
git log
```
本关要求记录下最新的 commit 对应的 hash 值.每个 commit 都会有一个独特的 hash 值来标识该 commit 的独特性, 而且 git log 打印出来的 commit 列表是按照时间先后顺序, 时间最晚的在
最前面.所以本关只需要将 git log 第一个 commit 的 hash 值记录下来回答问题即可.
## 17. tag
```
git tag new_tag
```
git tag tag_name 后面没有加 commit 的 hash 值默认为当前的 commit 加上 tag.
## 18. push tags
```
git push --tags origin master
```
将所有本地 commit 中有 tag 的推送到远程仓库中.这个命令通常用在一些批量的场合, 像需要对有特殊 tag 的 commit 进行 docker 镜像打包.
## 19. commit amend
```
git status
git add forgotten_file.rb
git commit --amend
```
本关需要将遗忘添加的文件添加到缓存区但是不使用新的 commit 来完成.先使用 git status 来查看是哪个文件遗漏了, 然后使用 git add 命令将文件添加到缓存区, 然后使用 git commit --amend 
来修改当前 commit. 注意不要在该 commit 已经推送到远程仓库之后再进行 git commit --amend 操作, 因为这个操作会改变 commit hash 值并覆盖原 commit.
## 20. commit in future
```
git commit --date 2018-01-21
```
为 commit 提供一个未来的时间, 时间格式接受多种, 例如 2018-01-23 这样的, 在 linux 系统下可以直接使用 date -R 命令来查看当前时间, 在 windows 系统下可以使用 date 命令来查看日期.
可以使用简短的 2018-01-21, 也可以接受 Mon, 3 Jul 2006 17:18:43 +0200, 2006-07-03 17:18:43 +0200, Mon Jul 3 15L18:43 2006 这样的时间格式. 甚至可以接受 --date=format:relative:5.hours.ago 这样的相对时间.
所以本关在使用 git commit --date 的时候使用一个未来的时间即可.
## 21. reset
```
git status
git log // 通过 git log 查看 to_commit_first.rb 文件提交的 commit hash
git reset ${to_commit_first.rb commit hash}
git status // 确认 first 文件被 add, second 文件没有 staged
git commit -m "add first"
```
本关要求将缓存区的记录回退到 to_commit_first.rb 文件提交的时候, 不缓存 to_commit_second.rb 的修改, 所以通过 git reset 命令, 修改记录回退到想要的时间.
当然回退操作也可以通过 git reset HEAD^, HEAD^ 的意思就是将 HEAD 指针回退到上一步.
## 22. reset soft
```
git reset --soft HEAD^
```
本关要求回退上一步的 commit, 但是保留索引(index), 而 reset 有三个参数: soft, mixed, hard. soft 会将记录回退, 但是不将索引, 工作区的更改覆盖, mixed 会将记录与索引回退, 但是
不覆盖工作区的更改, hard 是完全将修改抛弃, 记录索引工作区的内容会全部被覆盖.
## 23. checkout file
```
git checkout -- config.rb
```
本关要求将 config.rb 的工作区修改全部覆盖, 不做保留, 保持与之前的文件内容一致.使用 git checkout 命令, 通过设置 -- filename 来保证只从远端拉取 config.rb 文件覆盖.
## 24. remote
```
git remote
```
查看 git 仓库添加的远程仓库名, 本关使用 git remote 查看并记录下远程仓库名回答问题.
## 25. remote url
```
git remote -v
```
和上一关基本一致, 添加 -v 参数可以查看远程仓库的仓库链接, 将远程仓库复制下来回答问题.
## 26. pull
```
git pull origin master
```
使用 git pull 命令从远程仓库拉取代码.
## 27. remote add
```
git remote add origin https://github.com/githug/githug
```
使用 git remote add 命令来添加远程仓库. origin 是远程仓库名, 后面接仓库 url.
## 28. push
```
git status
git rebase origin/master
git push origin master
```
使用 rebase 与远程的 master 分支进行变基合并, 然后将更改推送到远端.
## 29. diff
```
git status
git diff app.rb
```
使用 git diff 命令查看 app.rb 文件哪里被修改了.查看哪一行被修改了, 本关答案为: 26. 其实 git diff 不能精确获得修改行数, 我们可以通过 git blame -p app.rb 查看, 可以在
bash 中看到在 26 行会有 author: Not Committed Yet 这样的信息, 对应行就是修改了的行.
## 30. blame
```
git blame config.rb
```
通过 git blame 命令快速找到指定文件的某一行最近修改的作者, 提交的 commit 及其时间.在团队协作中能够快速找到该行代码是谁改动了. 本关答案是 Spider Man.
## 31. branch
```
git checkout -b test_code
```
本关是为了展示分支的好处, 通过新建一个分支, 我们则可以在分支上进行我们对功能的实验性代码的编写而不影响原分支.当然上面的分支是缩写, 你也可以:
```
git branch test_code
git checkout test_code
```
## 32. checkout
```
git checkout -b my_branch
```
和上一关是一样的, 新建一个名为 my_branch 的分支.
## 33. checkout_tag
```
git checkout v1.2
```
本关要求检出到 tag 为 v1.2 的分支代码上.
## 34. checkout_tag_over_branch
```
git tag -l
git checkout tags/v1.2
```
本关要求将代码检出到 tag 为 v1.2 的代码,但是不能直接使用 git checkout v1.2, 因为仓库中有一个名为 v1.2 的分支, 如果直接使用会切换到 v1.2 分支上, 所以应该先使用 git log 来查看
tag, 然后使用 git chekcout 切换 tag 代码.
## 35. branch_at
```
git log
git checkout -b test_branch <commit hash>
```
本关要求在最后一个 commit 前的一个 commit 上新建一个分支, 所以可以使用 git log 查看 commit 历史, 然后将需要的 commit hash 复制下来在 git checkout 中使用.
## 36. delete_branch
```
git branch -d delete_me
```
删除分支可以使用 git branch 命令, 使用 -d 参数, 指定需要删除的分支名.
## 37. push_branch
```
git push --set-upstream origin test_branch
```
本关要求只向远程仓库推送本地 test_branch 分支上的修改, 可以使用 --set-upstream 参数来达到目的.
## 38. merge
```
git checkout master
git merge feature
```
本关要求需要将 feature 分支合并到 master 分支, 如果不在 master 分支则需要先 git checkout master 分支然后再进行 merge.
## 39. fetch
```
git fetch
```
从远程仓库获取最新的提交的更改, 但不与本地仓库合并.
## 40. rebase
```
git checkout feature
git add .
git commit -m "ready to rebase"
git rebase master
```
将 feature 分支通过 rebase master 达到历史记录为一条平滑的曲线.
## 41. rebase_onto
```
```