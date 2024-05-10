# Git教程笔记 4.21

【GeekHour】一小时Git教程 https://www.bilibili.com/video/BV1HM411377j/?p=6&share_source=copy_web&vd_source=603c1ecf4a2efddfbd14a032be6befff

## 1 课程简介 

git是一种分布式版本控制系统，可以跟踪每个项目的变化。

### 1.1 集中式和分布式版本控制系统

##### 集中式 SVN：中央处理器的单点故障会引起巨大损失

![image-20240330194226559](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20240330194226559.png)

##### 分布式 Git

![image-20240330194315633](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20240330194315633.png)

## 2 安装和初始化配置

### 2.1 git的使用方式

**(1)** 命令行 **(2)** 图形化界面(GUI) **(3)** IDE插件/扩展

### 2.2 姓名邮箱等初始化

![image-20240330195816893](C:\Users\86133\AppData\Roaming\Typora\typora-user-images\image-20240330195816893.png)

git常用命令资料见GeekHour公众号

## 3 新建仓库

版本库/仓库 （Repository简称Repo）

```shell
git init
git clone
```

![image-20240420232215938](images/image-20240420232215938.png)

## 4 Git的工作区域和文件状态

**Git的本地数据管理分为三个区域**

**工作区（Working Directory）：**自己工作的目录，本地资源管理器看到的目录

**暂存区（Staging Area/Index）：**临时存储区域，用于保存即将提交到Git仓库的修改内容

**本地仓库（Local Repository）：**我们用 git init 创建的目录，是Git存储代码和版本信息的主要位置

![image-20240420232926216](images/image-20240420232926216.png)

![image-20240420233113899](images/image-20240420233113899.png)

**车间不需要每次生产都提交到本地仓库，可以先放到暂存区。**

## 5 git add & git commit

![image-20240420233201906](images/image-20240420233201906.png)

![image-20240420235530496](images/image-20240420235530496.png)

## 6 git reset

回退到指定版本

![image-20240421000404529](images/image-20240421000404529.png)

其中`git reset --soft`、`git reset --mixed`比较常用

用于撤销某几次提交，当认为多次提交没必要时把多次提交改为一次性提交；

而`git reset --hard`不常用，使用`git reflog`找到提交版本号，再使用`git reset --hard 版本号` 回溯已经commit的内容。

## 7 git diff

![image-20240423000500251](../AppData/Roaming/Typora/typora-user-images/image-20240423000500251.png)

什么都不加的话默认是工作区和暂存区的区别

git diff

暂存区和版本库

git diff HEAD/git diff --cached

不同版本之间

git diff 版本1提交ID 版本二2提交ID 

提交ID可用HEAD替代HEAD表示当前，HEAD^或HEAD~表示前一个版本，HEAD~n表示前n个版本

还可以在语句后加指定文件名指定对比特定文件

git diff 版本1提交ID 版本二2提交ID 文件名

![image-20240423001910481](../AppData/Roaming/Typora/typora-user-images/image-20240423001910481.png)

![image-20240423001938893](../AppData/Roaming/Typora/typora-user-images/image-20240423001938893.png)

## 8 git rm

直接使用rm只能删除工作区的文件，需要 git add + git commit 才能删除暂存区和本地仓库的东西

使用git ls-files查看暂存区内容

用 git rm 可以删除和工作区和暂存区，然后要再用git commit 更新

## 9 .gitignore忽略文件

![image-20240509182633419](../AppData/Roaming/Typora/typora-user-images/image-20240509182633419.png)