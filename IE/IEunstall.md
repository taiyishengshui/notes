系统：Windows 7， 全新安装，安装完成后，（该剁手）装了IE11，后悔了，要换IE10。  
1，用“控制面板”=》“程序和功能”=》左侧选项“打开或关闭Windows功能”=》在新窗口，去除勾“Internet Explorer 11”，点确定，等待完成。  
2，依次点击“开始>所有程序>附件”，右键点击“命令行提示符”，选择“以管理员身份运行”。  
3，复制以下命令：  
```
FORFILES /P %WINDIR%\servicing\Packages /M Microsoft-Windows-InternetExplorer-*11.*.mum /c "cmd /c echo Uninstalling package @fname && start /w pkgmgr /up:@fname /norestart"
```
4，复制后，右键点击“命令提示符”窗口，选择“粘贴”，粘贴命令后，按回车键运行此命令。 
5，运行完成后，请重新启动计算机，打开IE，查看IE11是否卸载成功并还原至IE8版本。  
6，如果系统IE已经退回IE8，你就可以安装其他版本的IE了。  
=========== END ==========  
P.S. 如果你要卸载其他版本的IE，请将命令中的“Microsoft-Windows-InternetExplorer-*11.*.mum”的数字11改为你所需的版本，9，10之类：“Microsoft-Windows-InternetExplorer-*9.*.mum”  
