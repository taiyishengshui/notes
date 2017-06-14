1、使用快捷键组合“Win+R”调出运行命令框，键入 regedit.exe，回车，打开注册表编辑器。
	（若弹出用户账户控制窗口，请允许以继续）

2、小易提示: 如果注册表修改不当可能会出现严重的问题。因此，请确保您认真执行这些步骤。为增加保护，请修改之前备份注册表。

定位到注册表键值：HKEY_CLASSES_ROOT\Excel.Sheet.12\shell\Open

右击，选择“导出”。在修改之前，我们先为其做一下备份。

3、做好备份后，就可以大胆修改了。

修改 Open\command 值。

展开“Open\command”，在右边细节窗口: 

双击打开“默认”，将其键值改为"C:\Program Files\Microsoft Office\Office14\EXCEL.EXE" "%1"
（如果您使用的是 Office 2007, 把 Office 14 改为 Office 12。另外，千万不要丢了引号）

4、然后，双击 command，将鼠标光标移到数值数据最后，用"%1"代替/dde
（如果使用的是 Office 2007， 用"%1"代替/e）

5、重命名 Open\ddeexec。

选中“ddeexec”，右击，选择“重命名”。为其取个新名字，例如“ddeexec2”。

6、用相同的办法，对 HKEY_CLASSES_ROOT\Excel.Sheet.8\shell\Open 进行备份和修改。 

