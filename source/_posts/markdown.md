---
title: Markdown的使用方法
date: 2021-07-19 07:44:00
tags: tools
---

## Markdown是什么

- Markdown 是一种轻量级标记语言，易读易写的纯文本格式编写文档。

- 2004 由约翰·格鲁伯（英语：John Gruber）创建。

- Markdown 编写的文档可以导出 HTML 、Word、图像、PDF、Epub 等多种格式的文档。

- Markdown 编写的文档后缀为 **.md**, **.markdown**。

  

## 标题

- 使用# 来设置标题  （快捷方式设置标题）

  ```java
  # 一级标题
  ## 二级标题
  ### 三级标题
  #### 四级标题
  ##### 五级标题
  ###### 六级标题
  ```
  <img src="C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210627171619759.png" alt="image-20210627171619759" style="zoom: 50%;" />

  **重点： #+空格+输入内容**

## 段落格式

### 字体

- **加粗**   

  ```
  **加粗**
  ```

- 斜体

  ``` java
  *斜体*
  ```

- ***斜体加粗***

  ```java
  ***斜体加粗***
  ```



### 段落

helloworld  

```java
段落的末尾两个上的空格以上加上回车，段落后出现一个空行重新出现一个新的段落
```



### 分割线

- 用三个以上*  -  建立分隔线  **中间可以出入空格**
```
****  
* * * * 
----
- - - -
```

****
* * * *
----
- - - -



### 下划线

- 使用<u>的标签设置

```java
<u>下划线</u>
```

<u>下划线</u>



### 删除线

- 两端加上两个波浪线 **~~** 

```
~~hello，world~~  
```

~~hello，world~~



### 注脚

```
[^注脚内容]
```

hello world

[^注脚内容]: 内容添加



## 列表

- 1234  有顺序列表标记 （输入数字+ .  + 空格 +回车）
  1. 内容1
  2. 内容2
  3. 内容3
  4. 内容4

- 无序列表 (*) (-) (+ ) + 空格 +回车   
- 列表嵌套   tab键

* 内容1
  * 内容1-1

## 区块  引用

- 段落开头使用（>） + 空格  

  ```
  > 内容1
  > > 内容2
  > > > 内容3
  ```

  > 内容1
  >
  > > 内容2
  > >
  > > > 内容3

- 引用别人的内容使用 （>）+ 输入内容

> Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。



## 代码 

```
```java +回车    可以指定语言
```

<img src="C:\Users\xuchu\AppData\Roaming\Typora\typora-user-images\image-20210627184001314.png" alt="image-20210627184001314" style="zoom: 80%;" /

## 图片

- 开头！

- 【  】 图片的解释说明

- （）图片的地址

  ** 可以是本地图片，也可输入图片网址**

```
![alt 属性文本](本地图片地址)  本地图片

![alt 属性文本](图片网址)   网上图片链接地址
```



 ![ダウンロード](C:\Users\xuchu\Desktop\ダウンロード.jpg)

<img src="https://mmbiz.qpic.cn/mmbiz_jpg/HDicsOGPowWLeicdNJxyH0piaJX463yNrNXdgUDy5ZibBOy1yzuH0J3VO4jYObTQ6LJy9hicI2icm9gaZcjjXzvCd2UQ/640?wx_fmt=jpeg" style="zoom:33%;" />

```
<img src="https://mmbiz.qpic.cn/mmbiz_jpg/HDicsOGPowWLeicdNJxyH0piaJX463yNrNXdgUDy5ZibBOy1yzuH0J3VO4jYObTQ6LJy9hicI2icm9gaZcjjXzvCd2UQ/640?wx_fmt=jpeg" style="zoom:33%;
```

超链接

```
[链接名称](链接地址)
```

[google](https://www.google.com/)

```
<https://www.google.com/> 或者直接使用链接地址 <输入链接地址>
```

<https://www.google.com/



**高级链接**

- 变量赋值的方法链接网站内容

```
参考文献 1 作为网址变量 [Google][1]
参考文献2 作为网址变量 [Baidu][2]
然后在文档的结尾为变量赋值（网址）

  [1]: http://www.google.com/
  [2]: https://www.baidu.com/
```

参考文献 1 作为网址变量 [Google][1]
参考文献 2 作为网址变量 [Baidu][2]
文档的结尾为赋值（网址）

[1]: http://www.google.com/
[2]: https://www.baidu.com/



## 表格

- 使用 **|** 来分隔不同的单元格，使用 **-** 来分隔表头和其他行。

```
|name |sex|birthday|
|--|--|--|
|小王|女|18|
|小李|男|21|

```

| name | sex  | birthday |
| ---- | ---- | -------- |
| 小王 | 女   | 18       |
| 小李 | 男   | 21       |

**对齐方式**

- **-:** 设置内容和标题栏居右对齐。
- **:-** 设置内容和标题栏居左对齐。
- **:-:** 设置内容和标题栏居中对齐。

```
|name |sex|birthday|
|-:--|:-:--|---:|
|小王|女|18|
|小李|男|21|
```

| name | sex  | birthday |
| ---- | ---- | -------: |
| 小王 | 女   |       18 |
| 小李 | 男   |       21 |

