# Git教程笔记

【GeekHour】一小时Git教程 https://www.bilibili.com/video/BV1HM411377j/?p=6&share_source=copy_web&vd_source=603c1ecf4a2efddfbd14a032be6befff

## 1 课程简介 

git是一种分布式版本控制系统，可以跟踪每个项目的变化。

### 1.1 集中式和分布式版本控制系统

##### 集中式 SVN：中央处理器的单点故障会引起巨大损失

![image-20240330194226559](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240330194226559.png)

##### 分布式 Git

![image-20240330194315633](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240330194315633.png)



## 2 安装和初始化配置

### 2.1 git的使用方式

**(1)** 命令行 **(2)** 图形化界面(GUI) **(3)** IDE插件/扩展

### 2.2 姓名邮箱等初始化

![image-20240330195816893](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240330195816893.png)



## 3 新建仓库( *git init* )

版本库/仓库 （Repository简称Repo）

```shell
git init
git clone
```

![image-20240420232215938](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240420232215938.png)



## 4 Git的工作区域和文件状态

**Git的本地数据管理分为三个区域**

**工作区（Working Directory）：**自己工作的目录，本地资源管理器看到的目录

**暂存区（Staging Area/Index）：**临时存储区域，用于保存即将提交到Git仓库的修改内容

**本地仓库（Local Repository）：**我们用 git init 创建的目录，是Git存储代码和版本信息的主要位置

![image-20240420232926216](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240420232926216.png)

![image-20240420233113899](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240420233113899.png)

**车间不需要每次生产都提交到本地仓库，可以先放到暂存区。**



## 5 添加和提交文件( *git add & git commit* )

![image-20240420233201906](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240420233201906.png)

![image-20240420235530496](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240420235530496.png)

常用：`git commit -am "一些说明"`。



## 6 回退到指定版本( *git reset* )

回退到指定版本

![image-20240421000404529](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240421000404529.png)

其中`git reset --soft`、`git reset --mixed`比较常用。

用于撤销某几次提交，当认为多次提交没必要时把多次提交改为一次性提交；

而`git reset --hard`不常用，使用`git reflog`找到提交版本号，再使用`git reset --hard 版本号` 回溯已经commit的内容。



## 7 查看不同版本或分支之间的差异( *git diff* )

![image-20240423000500251](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240423000500251.png)

什么都不加的话默认是工作区和暂存区的区别: `git diff`

暂存区和版本库: `git diff HEAD/git diff --cached`

不同版本之间: `git diff 版本1提交ID 版本二2提交ID` 

提交ID可用HEAD替代HEAD表示当前，HEAD^或HEAD~表示前一个版本，HEAD~n表示前n个版本

还可以在语句后加指定文件名指定对比特定文件: `git diff 版本1提交ID 版本二2提交ID 文件名`

![image-20240423001910481](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240423001910481.png)

![image-20240423001938893](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240423001938893.png)



## 8 删除文件( *git rm* )

直接使用`rm`只能删除工作区的文件，需要 `git add + git commit` 才能删除暂存区和本地仓库的东西

使用`git ls-files`查看暂存区内容

用 `git rm` 可以删除和工作区和暂存区，然后要再用`git commit` 更新



## 9 忽略文件( *.gitignore* )

![image-20240509182633419](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240509182633419.png)

在文件中列出需要忽略的文件

![image-20240709175756944](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709175756944.png)

![image-20240709175828150](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709175828150.png)



> github上.gitignore预设
>
> [github/gitignore: A collection of useful .gitignore templates](https://github.com/github/gitignore)



## 10&11  Github账号创建 & SSH配置和克隆仓库( *git clone* )

![image-20240709210853500](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709210853500.png)

![image-20240709211448840](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709211448840.png)



## 12 关联本地仓库和远程仓库 ( *git remote & git pull & git push* )

![image-20240709212206304](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709212206304.png)



## 13 Gitee和GitLab

可以把本地仓库同时关联GitHub/Gitee/GitLab的远程仓库



## 14 GUI工具



## 15 VSCode中使用Git



## 16 分支简介和基本操作

![image-20240709214523608](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709214523608.png)

![image-20240709215210591](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709215210591.png)

![image-20240709215319956](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709215319956.png)

![image-20240709215516638](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709215516638.png)



## 17 解决合并冲突( *git merge* )

![image-20240709215828367](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709215828367.png)

可以使用`git diff` 查看，然后手动合并

![image-20240709220007149](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709220007149.png)

![image-20240709220033593](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709220033593.png)



## 18 回退和变基( *git reset & git rebase* )

![image-20240709220313666](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709220313666.png)

**git merge 和 git rebase的区别**

前者方便查看提交历史和回滚，后者形成线性历史



## 19 分支管理和工作流模型

Git Flow模型、GitHub Flow模型

![image-20240709221645275](https://github.com/slowdowndown/Mymdimage/blob/main/image-20240709221645275.png)



## 附 Git CheetSheet byGeekHour

![Git-Cheet-Sheet-ByGeekHour](https://github.com/slowdowndown/Mymdimage/blob/main/Git-Cheet-Sheet-ByGeekHour-17205348236071.png)
