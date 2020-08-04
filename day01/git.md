- [概述](#概述)
- [注册GitHub](#注册github)
- [注册码云](#注册码云)
- [安装Git](#安装git)
- [使用Git、码云管理项目（必会）](#使用git码云管理项目必会)
  - [初始化项目到本地](#初始化项目到本地)
  - [提交代码](#提交代码)
  - [冲突解决](#冲突解决)

## 概述

- git是一款软件，而github和码云(gitee)都是web开发流程代码托管平台。

## 注册GitHub

- https://github.com/

## 注册码云

- https://gitee.com/

## 安装Git

- https://git-scm.com/

- 也叫版本控制工具，svn、cvs

- 安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功

- 或者打开cmd，输入`git --version`出现版本号，也说明安装成功

## 使用Git、码云管理项目（必会）

> 以下以码云平台操作为主，Git操作类似。

- 创建仓库(项目)

    1. 右上角点击+号，选择“仓库名称”
    2. 输入“仓库名称”-“仓库介绍”-“是否开源”-选择“使用Readme文件初始化这个仓库”，点击“创建”，仓库介绍会出现在README.md文件中，“选择语言”-项目中所用的语言和“添加 .gitignore”-提交时忽略某些文件的配置文件，不选即可，“选择分支模型”默认单分支即可，如果想要创建额外分支，以后用命令创建即可。
    3. 进入到新建的仓库中，点击右上角“管理”，在“删除仓库”里面可以删除该项目

### 初始化项目到本地

- 项目管理-以下命令都在“git bash”中操作

    - 名字和Email地址设置

    ```
        git config --global user.name "Your Name"
        git config --global user.email email@example.com

    ```

    - 查看配置所有的信息

    ```
        git config --list

    ```

    - 创建SSH Key

    ```
        1. ssh-keygen -t rsa -C "密钥注释"
        2. 设置key保存目录，默认即可
        3. 输入密码，默认为空即可
        4. 再次输入密码，默认为空即可
        5. 打开目录“C:\Users\Administrator\.ssh”即可看到生成的SSH Key
        6. 用ide编辑器或者浏览器打开“id_rsa.pub”文件
        7. 复制里面的key值
        8. 点击右上角头像，点击“设置”，点击左侧“SSH公钥”，输入“标题（随便输入个标识）”-“公钥（里面填刚才复制的key值）”，点击“确定”
        9.  输入密码验证一下，就可以成功添加公钥

    ```

    - 从远程库克隆

    ```
        1. 选择一个目录
        2. 输入git clone git地址

    ```

### 提交代码

- 把文件添加到版本库

```
    1. 输入“cd test”进入到test目录下
    2. 输入“git add 文件1 文件2”添加要提交的文件到暂存区

```

- 添加所有文件

```
    git add .

```

- 查看暂存区中文件信息

```
    git ls-files

```

- 撤销指定暂存区中文件

```
    git reset HEAD -- filename

```

- 撤销所有暂存区中文件

```
    git reset HEAD --

```

- 提交版本日志

```
    - git commit -m "wrote a readme file"
    - -m 参数表示可以直接输入后面的message。

```

- 更新远程库内容

```
    git pull origin master

```

- 把本地库的所有内容推送到远程库上

```
    git push -u origin master

```

> 第一次推送master分支时可以使用-u选项指定一个默认主机，这样后面就可以不加任何参数使用git push。

### 冲突解决

- 冲突的形式：

```
    <<<<<<< HEAD
    你要提交的代码
    =======
    同事已经提交的代码
    >>>>>>>
```

- 自我判断谁的代码是正确的，如果无法判断就去邀请起冲突的同事一起判断最后要留谁的代码
- 将冲突解决后，得重新提交

```
    git add test.html
    git commit -m "conflict fixed"
    git push

```

> 更多git命令请参考：https://www.liaoxuefeng.com/wiki/896043488029600/900003767775424

    
    








    




    

