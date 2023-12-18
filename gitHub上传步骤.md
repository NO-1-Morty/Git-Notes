## Git上传项目到Github仓库教程

### 介绍

- **Git**：一个开源的分布式版本控制工具。
- **Github**： 一个面向开源及私有软件项目保存用户的数据、代码等文件的托管平台。

### 准备阶段

#### Github&创建仓库

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144027755.png" alt="image-20231218144027755" style="zoom: 50%;" />



#### 安装git客户端；

> Git官网地址： [https://git-scm.com/](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fgit-scm.com%2F&source=article&objectId=2068287)

**下载**

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144302423.png" alt="image-20231218144302423" style="zoom:50%;" />

##### Git官方版

- [Windows版](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fgit-scm.com%2Fdownload%2Fwin&source=article&objectId=2068287)
- [Mac版](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fgit-scm.com%2Fdownload%2Fmac&source=article&objectId=2068287)
- [Linux版](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fgit-scm.com%2Fdownload%2Flinux&source=article&objectId=2068287)

------

##### Git-GUI版

- [WindowsGUI版](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fgit-scm.com%2Fdownload%2Fgui%2Fwindows&source=article&objectId=2068287)
- [MacGUI版](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fgit-scm.com%2Fdownload%2Fgui%2Fmac&source=article&objectId=2068287)
- [LinuxGUI版](https://cloud.tencent.com/developer/tools/blog-entry?target=https%3A%2F%2Fgit-scm.com%2Fdownload%2Fgui%2Flinux&source=article&objectId=2068287)

选择适合的版本进入下载，按照安装向导完成安装，不需要配置其他的东西，直接Next。

下面以Windows官方版进行演示，其他操作系统操作一致。

### 连接仓库

#### Git配置

1.选择要上传的文件，右键鼠标选择 `Git Bash Here`

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144404127.png" alt="image-20231218144404127" style="zoom:50%;" />

2.输入命令 `ssh-keygen -t rsa -C "your email@youremail.com" `,按提示输入一直回车即可生成秘钥，找到秘钥的文件路径。

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144444278.png" alt="image-20231218144444278" style="zoom:50%;" />



3.在文件夹中打开秘钥所在路径然后选择 `id_rsa.pub` 右键以记事本方式打开，复制里面的秘钥

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144528109.png" alt="image-20231218144528109" style="zoom: 67%;" />

#### github配置

##### 创建SSH秘钥

1.点击头像 --> 点击`Settings`

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144632605.png" alt="image-20231218144632605" style="zoom: 67%;" />

2.点击 `SSH and GPG keys` --> 点击`New SSH Keys`

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144717094.png" alt="image-20231218144717094" style="zoom: 67%;" />



<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144735647.png" alt="image-20231218144735647" style="zoom:67%;" />



3.输入标题名称，然后粘贴从 `id_rsa.pub` 文件里复制的秘钥，点击 `Add SHH key` 

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144821653.png" alt="image-20231218144821653" style="zoom:50%;" />



4.验证连接，输入命令 `ssh -T git@github.com` 回车，根据提示输入 `yes`，出现图片中的提示就说明成功了。

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144848720.png" alt="image-20231218144848720" style="zoom:67%;" />

#### 配置用户信息

- 设置username和email，github每次commit都会记录这些信息。
	- 输入命令: `git config --global user.name "注册时填写的名字" `
	- 输入命令：`git config --global user.email "注册时填写的邮箱" `

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144909235.png" alt="image-20231218144909235" style="zoom:67%;" />



### 上传文件

> 上面的环节配置完毕后，下次上传只需要执行以下命令

选择要上传的文件，右键鼠标选择 `Git Bash Here`

1.输入命令 ` git init ` 将本地项目变成 Git 可以管理的仓库

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144933031.png" alt="image-20231218144933031" style="zoom:67%;" />

2.输入命令 ` git add . ` 将项目的所有文件添加到暂存区

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218144955020.png" alt="image-20231218144955020" style="zoom:80%;" />

3.输入命令 `git commit -m "自己项目提交的描述" ` 将项目文件提交到仓库

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218145039300.png" alt="image-20231218145039300" style="zoom:80%;" />



4.复制github仓库地址，点击 `Code` --> `SSH` --> 点击复制

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218145104166.png" alt="image-20231218145104166" style="zoom: 50%;" />



5.输入命令 ` git remote add origin 仓库地址链接 `，连接仓库

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218145139319.png" alt="image-20231218145139319" style="zoom: 67%;" />

6.输入命令 `git pull --rebase origin master或者main` 获取远程库与本地同步（远程仓库不为空需要这一步，这里的master或main是你当前项目的分支）

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218145234858.png" alt="image-20231218145234858" style="zoom:67%;" />

7.输入命令 `git push -u origin master/main` 上传代码到github远程仓库

<img src="../../../AppData/Roaming/Typora/typora-user-images/image-20231218145310426.png" alt="image-20231218145310426" style="zoom:67%;" />

### 更新文件

进入要更新的项目文件根目录，右键鼠标选择 `Git Bash Here`

1.输入命令 `git status` 查看当前的git仓库状态

2.输入命令 `git add *` 添加全部更新

3.输入命令 `git commit -m "更新说明"` 添加说明到项目文件

4.输入命令 `git pull` 拉取当前分支最新代码，防止与他人更新代码冲突

5.输入命令 `git push origin master`  更新上传代码到github远程仓库



如果是首次使用Git命令行上传项目，那么在输入git push -u origin master将项目文件上传成功至GitHub仓库时，会弹出一个窗口需要用户输入自己的GitHub账号+密码。


 出现下面图片样例代表上传成功， 退出Git，刷新GitHub，可发现上传的项目文件了

![img](https://img-blog.csdnimg.cn/0c6c0b19530e404ea13539b316707c71.png)



如果出现以下错误，可以输入git remote rm origin先删除远程仓库链接，然后再次输入 git remote add origin你新建仓库地址链接。

```csharp
git remote add origin
```

![img](https://img-blog.csdnimg.cn/be5e9febf394453cb3017aff987541d3.png)

参考文章：[Git上传项目到Github仓库教程-腾讯云开发者社区-腾讯云 (tencent.com)](https://cloud.tencent.com/developer/article/2068287)

​					https://blog.csdn.net/qq_40379132/article/details/124927589
