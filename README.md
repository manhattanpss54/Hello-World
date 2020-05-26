# Hello-World



# GIT





##### Git配置

1. 首先要将本地和远程账户之间的身份能够进行认证。

设置**用户名**和**邮箱**。设置username和email（github每次commit都会记录他们）

```css
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

这里就写GitHub账户上的名字和你的邮箱。

![image-20200526202137770](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526202137770.png)

2. 通过终端命令创建ssh key

```css
ssh-keygen -t rsa -C "xxxxx@qq.com"
```

```css
localhost:Hello-World_For_Git yangqing$ ssh-keygen -t rsa -C "13@qq.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/yangqing/.ssh/id_rsa):  
/Users/yangqing/.ssh/id_rsa already exists.
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/yangqing/.ssh/id_rsa.
Your public key has been saved in /Users/yangqing/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:GrpT33Rdy1I6Aa2DhjbXoxvnAQ6Oak 1098433@qq.com
The key's randomart image is:
+---[RSA 3072]----+
|         .. .    |
|          .+ .   |
|        . =.+    |
|       + =.+ o...|
|      o S  .=.*+.|

|    ..      o=oo.|
+----[SHA256]-----+

```

终端查看`.ssh/id_rsa.pub`文件

```kotlin
open .ssh/id_rsa.pub 
```

进入到路径下，才可以进行操作！

vim打开这个公钥实在是太难受了，格式不能正常。

配置sublime在终端可以打开文本：

```css
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime
sublime id_rsa.pub
```

3. 登陆GitHub，添加SSH，点击Setting。

![image-20200526185737114](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526185737114.png)

添加SSH。

![image-20200526185822732](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526185822732.png)



![image-20200526185916615](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526185916615.png)

![image-20200526190055128](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526190055128.png)

4. 验证链接

```css
ssh -T git@github.com 
```

```css
Hi FocusYangQ! You've successfully authenticated, but GitHub does not provide shell access.
```

如果出现上面的内容，恭喜你！验证成功了！







##### 新建仓库

仓库初始化：GitHub可视化界面新建仓库

![image-20200526202815269](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526202815269.png)

![image-20200526203850611](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526203850611.png)





##### CLONE到本地仓库

Git演示的流程应该是从远程仓库拉取到本地，建立一个仓库。

1. 复制SSH。

![image-20200526204343874](/Users/yangqing/Library/Application Support/typora-user-images/image-20200526204343874.png)

2. CLONE到本地

进入一个文件夹，

```css
git clone git@github.com:FocusYangQ/Hello-World.git
```

git@github.com:FocusYangQ/Hello-World.git 就是刚刚复制的SSH路径。

这次的实验结果，也算是成功了。

```css
Cloning into 'Hello-World'...
Warning: Permanently added the RSA host key for IP address '13.250.177.223' to the list of known hosts.
warning: You appear to have cloned an empty repository.
localhost:Hello-World_For_Git yangqing$ ls
Hello-World	README.md
localhost:Hello-World_For_Git yangqing$ cd ..
localhost:Desktop yangqing$ git clone git@github.com:FocusYangQ/Hello-World.git
Cloning into 'Hello-World'...
warning: You appear to have cloned an empty repository.
```

将编辑好的代码（代码一定得是一个工程，IDEA中建立的工程）上传：

```css
//文件添加到暂存区（.代表提交所有文件）
git add .
//把文件提交到本地仓库
git commit -m "First Commit"
//上传到远程仓库
git push
```

git commit -m "First Commit" 终端完整输出如下

```css
[master 348935c] First Commit
 7 files changed, 246 insertions(+)
 create mode 100644 Hello-World-IDEA/.idea/encodings.xml
 create mode 100644 Hello-World-IDEA/.idea/misc.xml
 create mode 100644 Hello-World-IDEA/.idea/modules.xml
 create mode 100644 Hello-World-IDEA/.idea/workspace.xml
 create mode 100644 Hello-World-IDEA/Hello-World.iml
 create mode 100644 Hello-World-IDEA/src/Hello_World.java
 rename Hello World => Hello-World/Hello World (100%)
```

git push 终端完整输出如下

```css
Everything up-to-date
```



内部原生说明文档：

![截屏2020-05-26 下午5.58.21](/Users/yangqing/Desktop/截屏2020-05-26 下午5.58.21.png)