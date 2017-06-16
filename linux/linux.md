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
