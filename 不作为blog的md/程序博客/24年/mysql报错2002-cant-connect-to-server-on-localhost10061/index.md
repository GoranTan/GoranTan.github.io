# 



mysql连接navicat发生报错`2002-Can&#39;t connect to server on &#39;localhost&#39;(10061)`

![](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241207191017011.png)

网上查找之后发现这个帖子：

[解决 本地计算机上的MySQL80服务启动后停止的问题！！！_本地连接mysql80服务启动停止-CSDN博客](https://blog.csdn.net/weixin_45042272/article/details/109412284)

使用cmd管理员权限打开，在：`C:\Program Files\MySQL\MySQL Server 8.0\bin`目录下执行`net start MySQL80`

![image-20241207191532823](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241207191532857.png)

上图所示，mysql还是无法启动，这时我们可以打开MySQLServer8.0\data下面的后缀名为.err的文件，查看错误信息，一般地址是`C:\ProgramData\MySQL\MySQL Server 8.0\Data`

![image-20241207191650802](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241207191650843.png)

使用记事本打开，翻到最下面

![image-20241207191745342](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241207191745388.png)



不同的人报错情况不同，有人是3306端口被占用，可以参考：[解决 本地计算机上的MySQL80服务启动后停止的问题！！！_本地连接mysql80服务启动停止-CSDN博客](https://blog.csdn.net/weixin_45042272/article/details/109412284)，建议把日志发给ai查找原因。

从我提供的 MySQL 错误日志来看，MySQL 无法启动的主要问题是与`mysql.user`表相关的错误，以下是具体分析和解决方法

### 一、问题分析

1. 表结构损坏
   - 日志中多次出现`Column count of mysql.user is wrong. Expected 51, found 4. The table is probably corrupted`的警告，这表明`mysql.user`表的结构可能已经损坏。
   - 随后出现`Fatal error: Could not read the column &#39;authentication_string&#39; from table &#39;mysql.user&#39;. Please perform the MySQL upgrade procedure.`的错误，说明由于表结构损坏，MySQL 无法读取`authentication_string`列，并且提示需要进行 MySQL 升级操作。

### 二、解决方法

1. **修复`mysql.user`表**
   - 使用`mysql_upgrade`工具（推荐）
     - `mysql_upgrade`是 MySQL 提供的用于升级和修复系统表的工具。
     - 首先，停止 MySQL 服务。
     - 然后，在命令提示符中进入 MySQL 的bin目录，执行以下命令：
       - `mysql_upgrade -u root -p`
       - 这会提示你输入 root 用户密码，`mysql_upgrade`会检查和修复系统表，包括`mysql.user`表。
     - 修复完成后，重新启动 MySQL 服务，看看问题是否解决。

![image-20241207192642637](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241207192642691.png)

这个信息的意思是`mysql_upgrade` 工具现在已被废弃。它的功能已经被集成到 MySQL 服务器中，服务器在启动时会自动执行必要的升级操作。

解决办法是直接启动新版本的 MySQL 服务器，它会自动执行必要的升级操作。

```
mysqld --initialize --user=mysql
mysqld --console
```

![image-20241207193753079](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241207193753127.png)



从我提供的日志来看，MySQL 服务器已经成功启动，并且没有明显的错误。

这个时候打开navicat显示新的报错：

![image-20241207193828832](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241207193828886.png)

此时通过重装解决问题。

---

> 作者:   
> URL: https://gorantan.github.io/%E4%B8%8D%E4%BD%9C%E4%B8%BAblog%E7%9A%84md/%E7%A8%8B%E5%BA%8F%E5%8D%9A%E5%AE%A2/24%E5%B9%B4/mysql%E6%8A%A5%E9%94%992002-cant-connect-to-server-on-localhost10061/  

