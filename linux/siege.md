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
|no-follow:                        |                                ||
| - ad.doubleclick.net             | ||
| - pagead2.googlesyndication.com  |||
| - ads.pubsqrd.com                |||
| - ib.adnxs.com                   |||


```
Siege常用的参数有如下几个：

-c 或者 --concurrent=NUM : 用于指定并发人数
-r 或者 --reps=NUM       : 用于指定重复次数
-d 或者 --delay=NUM      : 用于指定延迟时间
-f 或者 --file=FILE      : 用于指定URL列表的文件，可以一次对多个路径进行测试
-t 或者 --time=NUMm      : 用于指定测试持续时间。例如： -t10S (10秒)  -t5M(5分钟)  -t1H(1小时)
-l 或者 --log[=FILE]     : 用于记录结果日志

```

```
Transactions:		          30 hits        ## 完成处理数30
Availability:		      100.00 %           ## 可用，成功率100%
Elapsed time:		        4.67 secs        ## 耗时4.67秒
Data transferred:	        0.07 MB          ## 数据传输0.07MB
Response time:		        0.50 secs        ## 响应时间0.50秒
Transaction rate:	        6.42 trans/sec   ## 每秒完成6.42个处理
Throughput:		        0.01 MB/sec          ## 吞吐量，每秒传输0.01MB
Concurrency:		        3.21             ## 实际最高并发连接数
Successful transactions:          30         ## 成功完成处理30次
Failed transactions:	           0         ## 失败0次
Longest transaction:	        2.25         ## 每次传输所花最长时间
Shortest transaction:	        0.37         ## 每次传输所花最短时间
```
```
Transactions: siege对服务器的访问次数。如果页面发生了redirect，那么siege会将跳转过的请求算成是另一个transaction
Availability: socket连接的成功率。算法是，如果页面发生了timeout,4xx,5xx，那么该请求算是失败请求，成功率就等于(所有请求-失败请求) / 总请求数
Elapsed time: 所有请求耗费的时间
Data transferred: 所有请求传输的数据量，包括请求的headers和content。所以这个数值可能比server端统计的数值要大一点
Response time: 平均响应时间
Transaction rate: Transactions / Elapsed time
Throughput: 每秒平均传输的数据量
Concurrency: 平均并发的请求数
Successful transactions: 所有status code < 400的transactions数量
Failed transactions: 所有status code >= 400的transactions数量
Longest transaction: 最耗时的请求时间
Shortest transaction: 最短单个请求时间
```



例子:
压测并发5人，重复两次
```
siege -c5 -r2 http://www.bing.com
```
在此基础上增加持续时间，设置为5秒

```
siege -c5 -r2 -t5S http://www.bing.com
```

siege支持https
```
sudo apt-get install openssl
sudo apt-get install libssl-dev
./configure -with-ssl=./configure --with-ssl
sudo make
sudo make clean
sudo make install
```
在安装前需要mack clean,否则https不生效，以下是搜索结果页  
https://stackoverflow.com/questions/42367606/siege-https-error-https-requires-libssl

