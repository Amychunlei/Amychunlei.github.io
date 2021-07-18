---
title: Git的使用方法
date: 2021-07-12 16:22:41
tags: 
- git
- nvidia
# - tags should be about the exact topic of the post
categories: 
- notes
- rant
# - categories should be about the type of post in relation to the website, it should NOT be about the topic of the post, which is left to "tags"
permalink: "git.html" 
# url of the post, should end with html, and convenient to have this field since changes are reflected instantly 
lang: 
# only set to override auto-detection (needed if not writing an English post, check _config.yml)
comments:
# whether to enable comments for post or not
summary: Setting up a dual-boot personal workstation with windows10/OpenSUSE leap 15.3 in 2021. 
# "Insert TL;DR about your post here"
---

# Git


##  git是什么

Git 是开源的分布式版本控制系统，主要是用于敏捷高效地处理任何或小或大的项目。



## 版本控制

版本控制（Revision control）是一种在开发的过程中用于管理文件、目录或工程等内 的修改历史

方便查看更改历史记录，备份以便恢复以前的版本的软件工程技术。

**特点：**

多人协作，记录跟踪历史记录，代码的安全和整合性等

**常见的版本控制工具：**

- **Git**
- **SVN**（Subversion）
- **CVS**（Concurrent Versions System）
- **VSS**（Micorosoft Visual SourceSafe）
- **TFS**（Team Foundation Server）
- Visual Studio Online

**本版控制分类**

- 本地版本控制---适用个人，每个版本做一个快照
- 集中版本控制 SVN
  - 所有版本数据在服务器上，从服务器上同步更新上传修改的代码
  - 缺点--不连网，无法切换版本，所有版本在服务器上一旦服务器损坏，将丢失所有数据
- 分布式版本控制 Git
  - 本地查看所有代码，离线可提交
  - 缺点--在本地拥有所有版本的代码，有安全隐患

## Git环境配置

打开[git官网](https://git-scm.com/)

下载git对应的系统版本

<img src="C:\Users\xuchu\Desktop\图片\image-20210627220903128.png" alt="image-20210627220903128" style="zoom:50%;" />





- 启动Git

<img src="C:\Users\xuchu\Desktop\图片\image-20210704145428357.png" alt="image-20210704145428357" style="zoom: 67%;" />



**Git  GUI ，Git Bash， Git CMD 的区别**

1. **Git GUI**--图形界面的git 
2. **Git Bash**--Unix与Linux风格的命令行
3. **Git CMD**--windows风格的命令行





## Git基本内容

### 常用的Linux命令

1. #表示注释

2. cd: 用来改变目录。

3. cd . . :回退到上一个目录，直接cd进入默认目录

4. cd . . /.. :回退到上的两个目录

5.  pwd : 显示当前所在的目录路径。

6. ls(ll): 列出当前目录中的所有文件，ll列出的内容更为详细。

7. ls -a: 列出当前目录中的所有文件,包括隐藏文件。

8. touch : 新建一个文件 如 touch hello.txt 就会在当前目录下新建一个hello.txt 文件。 

9. rm: 删除一个文件, rm hello.txt 就会把hello.txt文件删除。 

10. mkdir: 新建一个目录,就是新建一个文件夹。

11. rm -r : 删除一个文件夹, rm -r src 删除src目录 

    ```
     rm -rf / 在Linux中尽量不要使用，会删除电脑中全部文件
    ```

    

12. mv 移动文件, mv hello.txt src hello.txt 是要移动的文件, src 是目标文件夹,必须保证文件和目标文件夹在同一目录下。 

13. reset 重新初始化终端/清屏。

14. clear 清屏。

15. history 查看命令历史。 

16. help 帮助。 

17. exit 退出。



### Git配置

- **查看配置文件**

  - 查看配置

    ```!
    git config -l
    ```

    

  - 查看系统配置文件

    ```
    git config --system --list
    ```

    

  - 查看当前用户配置

    ```
    git config --global --list
    ```

-  **查看相关的配置文件**

  - system 系统级

    ```!
    Git\etc\gitconfig ：Git 安装目录下的 gitconfig 
    ```

    <img src="C:\Users\xuchu\Desktop\图片\image-20210704161548719.png" alt="image-20210704161548719" style="zoom:50%;" />

  - global全局

    ```!
    C:\Users\Administrator\ .gitconfig 只适用于当前登录用户的配置
    ```

- **设置用户名和邮箱**

  安装git后，需要设置用户名和邮箱地址，git内容的提交需要用户名和邮箱地址

  ```
  git config --global user.name "gitgit" #名称
  git config --global user.email 123456@qq.com #邮箱
  ```

## Git的理论知识

### Git的三个工作区域和一个远程仓库

**1.工作目录（Working Directory）**---存放代码操作修改的地方

**2.暂存区(Stage/Index)**--临时存放修改的文件，保存即将提交的的文件

**3.资源库 (Repository或Git Directory)**--仓库区，安全存放数据的位置，包括所有提交的版本数据 。**HEAD**是更新后的最新的版本

**4.Remote：**远程仓库，托管代码的服务器，用于远 程数据交换

<img src="C:\Users\xuchu\Desktop\图片\image-20210704152306387.png" alt="image-20210704152306387" style="zoom:50%;" />





**三个区域确切的说应该是git仓库中HEAD指向的版本：**

- Directory：使用Git管理的一个目录，也就是一个仓库，包含我们的工作空间和Git的管理空间。
- WorkSpace：需要通过Git进行版本控制的目录和文件，这些目录和文件组成了工作空间。
- .git：存放Git管理信息的目录，初始化仓库的时候自动创建。
- Index/Stage：暂存区，或者叫待提交更新区，在提交进入repo之前，我们可以把所有的更新放在暂存区。
- Local Repo：本地仓库，一个存放在本地的版本库；HEAD会只是当前的开发分支（branch）。
- Stash：隐藏，是一个工作状态保存栈，用于保存/恢复WorkSpace中的临时状态

![image-20210704155210835](C:\Users\xuchu\Desktop\图片\image-20210704155210835.png)

![image-20210704154830032](C:\Users\xuchu\Desktop\图片\image-20210704154830032.png)

git的工作流程一般是这样的：

１、在工作目录中添加、修改文件；

２、将需要进行版本管理的文件放入暂存区域；

３、将暂存区域的文件提交到git仓库。

因此，git管理的文件有三种状态：已修改（modified）,已暂存（staged）,已提交(committed)

![](C:\Users\xuchu\Desktop\图片\image-20210704154700237.png)

## Git项目搭建



工作目录（WorkSpace)用Git帮助你管理的文件夹

日常使用只要记住下图6个命令：

![image-20210704162126552](C:\Users\xuchu\Desktop\图片\image-20210704162126552.png)



### **本地仓库搭建**

- 创建全新的仓库

  在git管理项目的根目录下执行

  ```
  $ git init
  ```

- 克隆远程仓库

  将远程的服务器上的仓库备份到本地进行操作

  ```
  $ git clone [url]  # https://gitee.com/....
  ```

  

### **提交和修改**

```
git add	添加文件到仓库
git status	查看仓库当前的状态，显示有变更的文件。
git diff	比较文件的不同，即暂存区和工作区的差异。
git commit	提交暂存区到本地仓库。
git reset	回退版本。
git rm	删除工作区文件。
git mv	移动或重命名工作区文件。

```

### **提交日志**

```
git log	查看历史提交记录
git blame <file>	以列表形式查看指定文件的历史修改记录
```

### 远程操作

```
git remote	远程仓库操作
git fetch	从远程获取代码库
git pull	下载远程代码并合并
git push	上传远程代码并合并
```



## Git文本操作

**文件的四种状态**

- Untracked: 未跟踪, 此文件在文件夹中, 但并没有加入到git库, 不参与版本控制. 通过git add 状态变为Staged.
- Unmodify: 文件已经入库, 未修改, 即版本库中的文件快照内容与文件夹中完全一致. 
- Modified: 文件已修改
- Staged: 暂存状态. 执行git commit则将修改同步到库中,

**查看文件的状态**

```
#查看指定文件状态git status [filename]
#查看所有文件状态git status
# git add .                  添加所有文件到暂存区
# git commit -m "消息内容"    提交暂存区中的内容到本地仓库 -m 提交信息
```



**忽略文件**

1. 忽略文件中的空行或以井号（#）开始的行将会被忽略。

2. 可以使用Linux通配符。

   星号（*）代表任意多个字符，问号（？）代表一个字符，方括号（[abc]）代表可选字符范围，大括号（{string1,string2,...}）代表可选的字符串等。

3. 文件名称前有感叹号（!），表示例外规则，将不被忽略。

4. 文件名称最前面是一个路径分隔符（/），表示要忽略的文件在此目录下，而子目录中的文件不忽略。

5. 如果名称的最后面是一个路径分隔符（/），表示要忽略的是此目录下该名称的子目录，而非文件（默认文件或目录都忽略）。

```
*.txt        #忽略所有 .txt结尾的文件
!aaa.txt     #aaa.txt除外
/temp        #仅忽略项目根目录下文件,不包括目录temp文件下的内容
build/       #忽略build/目录下的所有文件
doc/*.txt    #会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
```

## 

**Git分支中常用的指令**

```
# 列出所有本地分支git branch
# 列出所有远程分支git branch -r
# 新建一个分支，但依然停留在当前分支git branch [branch-name]
# 新建一个分支，并切换到该分支git checkout -b [branch]
# 合并指定分支到当前分支$ git merge [branch]
# 删除分支$ git branch -d [branch-name]
# 删除远程分支$ git push origin --delete [branch-name]$ git branch -dr [remote/branch]
```

## 

