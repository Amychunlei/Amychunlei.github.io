---
title: hexo的使用方法
date: 2021-07-19 07:43:26
tags: hexo
---
## 环境搭建

### 下载并安装Node.js

- 官网下载，选择相应版本

```java
https://nodejs.org/en/download/
```

<img src="C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210627214659156.png" alt="image-20210627214659156" style="zoom:50%;" />

- 安装后验证   cmd（Win+R）

  ```java
  node -v
  ```

  ![image-20210627215020257](C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210627215020257.png)

- 查看npm版本

  ```
  npm -v	
  ```

- 安装淘宝的cnpm 管理器

  ```
  npm install -g cnpm --registry=http://registry.npm.taobao.org
  ```

- 查看cnpm版本

  ```
  cnpm -v
  ```

- 环境变量设置

  ```java
  我的电脑 -> 属性 -> 高级系统设置 -> 环境变量  系统变量下的path变量，添加Node.js的地址
  ```

  


### 注册Gitub

- 官网注册 **Sign up**

  > https://github.com/

- 注册成功之后，创建库 (在Github的**+** 选择New repository）

  **注意GithubName.github.io** 

  Owner必须是你的github的名字

  Repository name必须是.github.io

  如果是其他创建不成功

  <img src="C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210629070243648.png" alt="image-20210629070243648" style="zoom: 50%;" />!(C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210629071605277.png)

<img src="C:\Users\xuchu\Pictures\スクリーンショット 2021-06-29 070716.png" alt="スクリーンショット 2021-06-29 070716" style="zoom:50%;" />



## 下载并安装Git

- 下载地址

  ```java
  https://git-scm.com/
  ```

  <img src="C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210627220920782.png" alt="image-20210627220920782" style="zoom: 33%;" /><img src="C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210627220903128.png" alt="image-20210627220903128" style="zoom:50%;" />

- 安装后验证     桌面点击鼠标右键，选择 **Git Bash Here**打开 或 Cmd (Win+R)  cmd（Win+R）

```java
分别输入查是否安装成功   git             git --version    
```

- **配置Git用户和邮箱**

  - 在桌面点击鼠标右键，点击 `Git Bash Here`

    ```
    git config --global user.name  #gituhub 的注册的用户名 
    
    git config --global user.xiaowang
    
    git config --global user.email  #gituhub 的注册的邮箱名
    
    git config --global user.1234@qq.com
    ```

  - 查看其他配置(git设置列表)

    ```
    git config --list  
    ```

    

## 本地安装hexo

- 安装hexo框架

  ```java
  cnpm install -g hexo-cli 
  ```

- 查看hexo版本

  ```
  hexo -v  
  ```

- 创建blog目录

  ```
  mkdir blog 
  ```

- 进入blog目录

  ``` java
  cd blog    
  ```

- 查看博客下生成的文件

  ```
  ls -l
  ```

- 生成博客 **初始化博客**

  ```
  sudo hexo init  
  ```

- 启动本地博客服务

  ```
  hexo s 
  http://localhost:4000/    # hexo 默认的一篇“Hello World”文章
  ```

  ![image-20210629082925027](C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210629082925027.png)

- 创建新的文章 

  ```java
  hexo n "我的第一篇文章"
  ```

- 返回blog**目录**

  ```java
  cd ../..
  ```

- 清理

  ``` java
  hexo clean 
  ```

- 生成

  ```java
  hexo g
  ```


- 在blog目录下安装git部署插件

  ```
  cnpm install --save hexo-deployer-git
  ```

- 补充

  ![image-20210629084535091](C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210629084535091.png

  ![image-20210629084603286](C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210629084603286.png)

  

## 博客发布到Github

- 在项目根目录下，安装发布的插件

  ```
  npm install hexo-deployer-git --save- 
  ```

- 修改项目配置文件：**_config.yml**

<img src="C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210629074432459.png" alt="image-20210629074432459" style="zoom: 67%;" />

**注意在type ： 之后有一个空格**

- 部署到Github仓库里

  ```
  hexo d 
  ```

- 访问这个地址可以查看博客

  ```
  https://YourGithubName.github.io/ 
  ```

  **文章Github上发布成功，不是在本地的网站**



## hexo博客主题安装

- 打开主题

```
cnpm install --save hexo-deployer-git
```

- 安装主题

  - themes/yilia 下载yilia主题到本地

```
 git clone https://github.com/litten/hexo-theme-yilia.git 
```

- 修改hexo根目录下的 _config.yml 文件 ：

  ```
  theme: yilia
  ```

- 清理一下

  ```
  hexo c	
  ```

- 生成

  ```
  hexo g
  ```

- 启动本地服务

  ```
  hexo s
  ```

- 部署到远程Github仓库  

  ```
  hexo-d
  https://YourGithubName.github.io/
  ```

  

## 文章发布流程

- 博客的根目录 /source/_posts 目录下，创建一个.md 文件进行编写

- 文件的顶部添加下面内容，主要写 title 就好了，其他可省略

  ![image-20210629091812978](C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210629091812978.png)

- 使用 **hexo g --d** 推送



 **或者**

![image-20210627220425254](C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210627220425254.png)



## 最后

如果有不理解的小伙伴，可以看一下[Codesheep](https://www.bilibili.com/video/BV1Yb411a7ty?from=search&seid=10602935136011786863)的视频，讲解比较详细，希望能够对你的博客搭建有帮助！

