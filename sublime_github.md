Sublime_GitHub设置教程
==============================
同样，首先在计算机上要先配置好Git。并且连接GitHub·
<!-- MarkdownTOC -->

- Sublime 安装Git插件
- 使用Git插件
- 添加远程GitHub仓库
- sublime 中使用插件命令

<!-- /MarkdownTOC -->
Sublime 安装Git插件
---------------------------
* 打开Package Control，选择install package ，然后输入git 之后安装。

如果安装失败，检查网络情况，或者需要更改插件安装镜像地址。

* 也可以单独下载插件包的形式进行安装，放在编辑器安装位置的Package目录下

然后添加git配置，需要在账户目录下找到“Git.sublime-setting"这个文件。
在其中添加

	"{git_command":"D:/IDE/Git/cmd/git.exe"}


使用Git插件
----------------------------
接下来进行git在sublime中的配置

1. 使用`shift+ctrl+p`打开命令窗口，输入`Git:init`来初始化git环境，会提示添加默认的git仓库，选择到你的工程目录就可以了
2. 使用`Git:status`来查看当前库的状态
3. 添加到缓存区：

	> `git:add`命令之后，选择`including untracked files`将新增文档添加到更改当中。

	> `git:commit`命令，用来提交。可以在文件最上方添加这次更改的comments。然后直接关闭就会发出commit操作。并将你输入的comments作为 -m参数提交。


添加远程GitHub仓库
--------------------------
首先GitHub上有一个repository,然后通过命令行连接远程仓库。
本地库目录下运行

	git remote add origin git@github.com:userName/`projectName`.git

这里添加的是你复制的GitHub项目上的ssh地址

* 工作目录下运行 git pull origin master 更新文件
* 工作目录下运行 git push origin master 提交文件

到GitHub查看下结果

sublime 中使用插件命令
------------------------------
·
1. 复制远程仓库ssh地址
2. 克隆项目到本地

		git clone git@github.com:userName/`projectName`.git

**用sublime打开项目**

1. git: Add All 将文件提交到暂存区
2. git: Commit 提交文件并添加注释
3. git: Push 上传至远程仓库

> 注意：在添加到远程库的时候，可能要到git本地仓库进行一次git add 和git commit
操作，因为在git版本苦衷，sublime的提交没有实现。然后再提交到远程库：git remote add origin....
然后还需要创建分支：git push -u origin master 创建提交分支
