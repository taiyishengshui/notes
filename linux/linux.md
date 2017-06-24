解决vim中文乱码的问题：  
打开vim的配置文件，位置在 /etc/vim/vimrc 在其中加入  

```
set fileencodings=utf-8,gb2312,gbk,gb18030  
set termencoding=utf-8  
set encoding=prc  
```
保存退出



对于gedit，解决方法如下：
在终端中运行 gconf-editor 
在打开的界面中选择： apps->gedit-2->preferences->encodings 
在右边的 auto_detected 和 shown_in_menu 上点右键编辑，点 add，分别加入GB2312(或者是GB18030）,并点 UP按钮移动到第一位。关闭，就可以在gedit中显示中文了.

github  
1/为了让github能够识别是我们自己上传文件，需要创建ssh key  
```
ssh-keygen -t rsa -C "your_email@youremail.com"
```

2/创建好本地的ssh key后,将生成的ssh key复制出来，写入github，在终端输入
```
cat ~/.ssh/id_rsa.pub
```

终端会显示出刚刚创建好的ssh key，复制出来，在github在点击头像，然后点击setting，在找到SSH and GPG keys，创建一个new ssh key，然后将刚刚复制的ssh key填入即可。

3/测试连通性
```
ssh -T git@github.com
```

4/设置commit的username和email，github会记录  
```
git config --global user.name "your name"
git config --global user.email "your_email@youremail.com"
```
5/添加远程仓库地址,yourName和yourRepo分别是你的github的用户名和仓库名。
```
git remote add origin git@github.com:yourName/yourRepo.git
```

xxx is not in the sudoers file. This incident will be reported的解决方法
1/进入超级用户模式。 
```
sudo su root
```
2/给sudoers写权限。
```
chmod u+w /etc/sudoers
```
3/编辑sudoers文件，输入"i"进入编辑模式，找到这一行：  
"root ALL=(ALL) ALL"
在下面添加. 
"xxx ALL=(ALL) ALL"(这里的xxx是你的用户名)，然后保存（就是先摁一 下Esc键，然后输入":wq"）退出。
```
vim /etc/sudoers
```
4/
```
chmod u-w /etc/sudoers
```


安装npm并替换为cnpm. 
Centos   
```
yum install -y nodejs
```
验证安装成功
```
node -v 
npm -v
```
替换淘宝源
```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

安装模块
```
cnpm install [name]
```
安装gitbook
```
cnpm install gitbook-cli -g
```
启动服务
```
gitboook serve
```
