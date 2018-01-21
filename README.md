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
这个是非常常用的命令, 
## 10.

## 11.

## 12.

## 13.

## 14.

## 15.

## 16.

## 17.

## 18.

## 19.

## 20.

## 21.

## 22.

## 23.

## 24.

## 25.

## 26.

## 27.

## 28.

## 29. diff
```
git diff app.rb
```
use git diff to find out 