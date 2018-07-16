# Daily_Bold_04

[TOC]



# `git`上传基本流程

## 刚安装好Git

### 1. 绑定用户

> `git config --global user.name "Rekol2333"`

> `git config --global user.email "Reol_Frank@163.com"`



### 2. Setup /  generates SSH Key.

#### 	1. Check out if had generated SSH key

> `cd ~/.ssh`

> `ls`

#### 	2. Generates SSH key.

> `ssh-keygen -t rsa -c "Reol_Frank@163.com"`

> 生成过程中一路按3次回车键就好了。（默认路径，默认没有密码登录） 生成成功后，去对应目录C:\Users\Rekol.ssh里用记事本打开id_rsa.pub，得到SSH key公钥。 

### 3. Add SSH key for github account.

- `settings` ---->`SSH KEYS`

> 点击Add SSH key新增密钥，填上标题（最好跟本地仓库保持一致）。 



## Upload to Repository in github.

### First enter one folder

#### 1. Enter the path which you wanted to upload.

> cd d:MarkAndMemory

>  `git init`

> 初始化成功后你会发现项目里多了一个隐藏文件夹.git 

### Upload the folder Normally

2. `git add .`
3. `git  commit -m "提交文件"`
4. `git remote add origin https://....`

> 复制仓库地址 

5. `git push -u origin master`

> upload local project.

_____



# Thanks: 

> ```
> 作者：hanyuntao
> 链接：https://www.jianshu.com/p/c70ca3a02087
> ```