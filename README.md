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
git commit --date=2018-01-21
```
为 commit 提供一个未来的时间, 时间格式接受多种, 可以简短
## 21. reset
```
```
## 22. reset soft
```
```
## 23. checkout file
```
```
## 24. remote
```
```
## 25. remote url
```
```
## 26. pull
```
```
## 27. remote add
```
```
## 28. push
```
```
## 29. diff
```
git diff app.rb
```
use git diff to find out 