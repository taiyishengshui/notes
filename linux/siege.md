1、获取源码，siege-lastest.tar.gz，一直是最新的  
```
 wget http://download.joedog.org/siege/siege-latest.tar.gz  
```
2、解压安装包
```
tar -xvf siege-latest.tar.gz
```
3、进入到siege 目录,当前版本是4.0.2所以可cd的是cd siege-4.0.2
```
cd siege-4.0.2
```
4、在siege-4.0.2目录下，运行./configure命令生成配置信息，这个命令会检查编译所需的库文件
```
./configure
```
5、编译和安装,make会生成一个二进制文件，make install将生成的二进制文件安装到指定的目录下。默认的安装目录是/usr/local/bin/
```
make
sudo make install
```
6、查看siege版本号
```
siege -V OR  siege --version
```
查看版本信息和默认配置参数：
|参数名                            |值                  |中文备注           |
|----------------------------------|--------------------------------|--------------------|
|version:                          |4.0.2                           |版本号|
|verbose:                          |true                            ||
|color:                            |true                            ||
|quiet:                            |false                           ||
|debug:                            |false                           ||
|protocol:                         |HTTP/1.1                        ||
|HTML parser:                      |enabled                         ||
|get method:                       |HEAD                            ||
|connection:                       |close                           ||
|concurrent users:                 |25                              | 指定用户数量|
|time to run:                      |n/a                             |测试时间，默认为n/a，没有指定|
|repetitions:                      |n/a                             |每个用户的请求数量，默认为n/a, 没有指定|
|socket timeout:                   |30                              ||
|accept-encoding:                  |*                               ||
|delay:                            |0.500 sec                       ||
|internet simulation:              |false                           ||
|benchmark mode:                   |false                           ||
|failures until abort:             |1024                            |超过一定数量停止测试|
|named URL:                        |none                            ||
|URLs file:                        |/usr/local/etc/urls.txt         ||
|thread limit:                     |255                             ||
|logging:                          |false                           ||
|log file:                         |/usr/local/var/log/siege.log    ||
|resource file:                    |/home/ubuntu/.siege/siege.conf  |资源文件，也就是配置以上参数的文件，文件路径为/usr/local/etc/siegerc|
|timestamped output:               |false                           ||
|comma separated output:           |false                           ||
|allow redirects:                  |true                            ||
|allow zero byte data:             |true                            ||
|allow chunked encoding:           |true                            ||
|upload unique files:              |true                            ||
|no-follow:
 - ad.doubleclick.net
 - pagead2.googlesyndication.com
 - ads.pubsqrd.com
 - ib.adnxs.com




