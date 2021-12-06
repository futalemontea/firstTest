# git的使用

## 1.git的安装

sudo apt updata

使用库安装：sudo apt-get install git

测试：git --version

## 2.git工作流程

![image-20211124172522987](/home/osuser/.config/Typora/typora-user-images/image-20211124172522987.png)

概念：

工作区：就是你在电脑里能看到的目录。
暂存区：英文叫 stage 或 index。一般存放在 .git 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
版本库：工作区有一个隐藏目录 .git，这个不算工作区，而是 Git 的版本库。

![image-20211124173617544](image-20211124173617544.png)

![image-20211128161655012](image-20211128161655012.png)

## 3.git常用命令

1）git项目创建

新建一个目录，在此目录下执行：git init

执行后，会创建一个隐藏.git目录

![image-20211124173302552](image-20211124173302552.png)

2)add

![image-20211128163026357](image-20211128163026357.png)

3)commit

提交文件到本地库

提交所有在staging area中的文件到registory：

git commit -m[message]

message是提交时的备注

![image-20211128163406505](image-20211128163406505.png)

![image-20211128164019040](image-20211128164019040.png)

4)push

上传远程代码到远程仓库并合并。

前提：远程有仓库。

![image-20211128170029688](image-20211128170029688.png)

url栏里就是远程仓库地址

先添加远程仓库：git remote add 别名 远程仓库url

![image-20211128170724435](image-20211128170724435.png)

错误的原因是没有指定远程的branch，需要指定为master。

注意：github页面上将master分支名改成了main，但push时还是需要用master，master对应web页面上的main

![image-20211128170804462](image-20211128170804462.png)

push时命令正确，认证失败：

![image-20211128171429415](image-20211128171429415.png)

获取token的方法：

![image-20211128171619718](image-20211128171619718.png)

点击右上角自己的图表，右上角选择settings



![image-20211128171849656](image-20211128171849656.png)

选Developer settings：

![image-20211128171941521](image-20211128171941521.png)

选择Personal access tokens

![image-20211128172113360](image-20211128172113360.png)

在页面上填上相关信息后

![image-20211128172433183](image-20211128172433183.png)

点击Generate token

![image-20211128172803904](image-20211128172803904.png)



关闭页面之前，需要把token拷贝出来，以后当成密码使用：

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

再次push：

![image-20211128173118091](image-20211128173118091.png)

password需要输入token。

5)clone

将远程仓库clone到本地:

git clone 远程仓库url

clone后操作步骤

（1）修改文件（project正常进程)

(2)add

(3)commit

(4)远程同步:

分支问题:从本地开始创建的项目，主分支是master；从远程开始，主分支是main。

a)添加远程仓库:

git remote add 别名 远程仓库url

git push

![image-20211201165628892](image-20211201165628892.png)

注意:password不能输入github的用户密码，而要输入token

6)diff

查看工作区和staging area的区别。

7）查看提交历史log

8）恢复reset

git reser --hard HEAD^1

回退到上一个版本，--hard将直接修改工作区文件内容

4.在vscode中使用git

1)用命令行进行git初始化

在vscode打开项目之前，已经执行了:git init,git add

在此目录下打开，可以直接用vscode

2)用vscode进行git初始化
