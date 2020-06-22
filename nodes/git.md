# 

<nav>
<a href="#Git简介">一、Git简介</a><br/>
<a href="#二、Git安装">二、Git安装</a><br/>
<a href="#三、常用Git命令">三、常用Git命令</a><br/>
    <a href="#四、Git的工作机制">四、Git的工作机制</a><br/>
    <a href="#五、分支操作">五、分支操作</a><br/>
    <a href="#六、GitHub">六、GitHub</a><br/>
</nav>




## 一、Git简介

1、GitHub是一个Git项目托管网站,主要提供基于Git的版本托管服务。

2、Git能干什么

```
1、版本还原
2、代码备份
3、冲突解决
4、权限管理
5、协同开发
6、历史追查
7、版本记录
8、分支管理
```

3、集中式版本管理与分布式管理

集中式经典代表：CVS、SVN、VSS

特点：由中央仓库统一管理，结构简单





git config --list 列出配置

git config --global user.name cc  配置全局用户名

git config --global user.email cc@qq.com  配置全局邮箱

git config --list --show-origin

git init 初始化

git status 查看



## 四、Git的工作机制

**1、三区**

工作区(Working Directory):就是你电脑本地硬盘目录

本地库(Repository):工作区有个隐藏目录.git，它就是Git的本地版本库

暂存区(stage):一般存放在"git目录"下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。

![Git-01](E:\BigData-Git\pictures\Git-01.png)

![Git-01](E:\BigData-Git\pictures\Git-02.png)









## 五、分支操作

**1.常用命令汇总**

| 命令                                       | 描述                                                         |
| ------------------------------------------ | ------------------------------------------------------------ |
| git branch [分支名]                        | 创建分支                                                     |
| git branch -v                              | 查看分支,可以使用-v参数查看详细信息                          |
| git checkout [分支名]                      | 切换分支                                                     |
| git merge [分支名]                         | 合并分支；  将merge命令中指定的分支合并到当前分支上  例如：如果想将dev分支合并到master分支，那么必须在master分支上执行merge命令 |
| git branch –d[分支名]                      | 删除分支                                                     |
| git checkout –b [分支名]                   | 新建并切换到当前分支                                         |
| git log --oneline --decorate --graph --all | 它会输出你的提交历史、各个分支的指向以及项目的分支分叉情况   |

**2.分支的概念**

不使用分支，就是人与人之间协作；

使用分支，就是小组与小组之间的协作；

从主干中拉取分支，开发完成，将工作，合并到主干。

**3、分支常用操作**

（1）查看分支

```
#git branch -v
git branch -v
```

（2）新建分支

```
#git branch [分支名]
git branch dev
```

（3）切换分支

```
#git checkout [分支名]
git checkout dev
```

（4）合并分支

要先切到master上才能合并分支

```
#git merge [分支名]
git merge dev
```

如果分支和master上有修改，合并分支时会有冲突

**处理分支冲突：**

```
编辑冲突的文件，把“>>>>>>>>>”、“<<<<<<”和“========”等这样的行删除，编辑至满意的状态，提交。
提交的时候注意：git commit命令不能带文件名。
```

然后

```
git add 文件
```

```
git commit -m “...”
```

最后

```
git merge dev
```

（5）删除分支

要先切换到master,才能删除，master不能自删

```
#git branch -d [分支名]
git branch -d dev
```

（6）新建切换

```
#git checkout -b [分支名]
git checkout -b dev
```