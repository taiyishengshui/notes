ϵͳ��Windows 7�� ȫ�°�װ����װ��ɺ󣬣��ö��֣�װ��IE11������ˣ�Ҫ��IE10��  
1���á�������塱=��������͹��ܡ�=�����ѡ��򿪻�ر�Windows���ܡ�=�����´��ڣ�ȥ������Internet Explorer 11������ȷ�����ȴ���ɡ�  
2�����ε������ʼ>���г���>���������Ҽ��������������ʾ������ѡ���Թ���Ա������С���  
3�������������  
```
FORFILES /P %WINDIR%\servicing\Packages /M Microsoft-Windows-InternetExplorer-*11.*.mum /c "cmd /c echo Uninstalling package @fname && start /w pkgmgr /up:@fname /norestart"
```
4�����ƺ��Ҽ������������ʾ�������ڣ�ѡ��ճ������ճ������󣬰��س������д���� 
5��������ɺ��������������������IE���鿴IE11�Ƿ�ж�سɹ�����ԭ��IE8�汾��  
6�����ϵͳIE�Ѿ��˻�IE8����Ϳ��԰�װ�����汾��IE�ˡ�  
=========== END ==========  
P.S. �����Ҫж�������汾��IE���뽫�����еġ�Microsoft-Windows-InternetExplorer-*11.*.mum��������11��Ϊ������İ汾��9��10֮�ࣺ��Microsoft-Windows-InternetExplorer-*9.*.mum��  
