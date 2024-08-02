# postgresql CentOS 7 安装以及设置

## 通过yum安装

1. Download PostgreSQL Repository RPM

```shell
sudo yum install -y https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm

```

 
2. Install PosgreSQL on CentOS 7

```shell
sudo yum install -y postgresql15-server
```

3. Initialize the Database
```shell
sudo /usr/pgsql-15/bin/postgresql-15-setup initdb

```

 
4. Start the Database

```shell
sudo systemctl start postgresql-15

```

6. （可选）Enable PostgreSQL Launch on Reboot

```shell
sudo systemctl enable postgresql-15

```

到此，已经初始化按错成功了。但是，目前只能在本地访问。需要再进行其他操作，开启ip访问。

## 修改默认的postgres密码

1. 切换用户postgres

```shell
sudo su - postgres
```
2. 登陆psql
   
```shell
psql
```
3. 修改密码
   
```shell
ALTER USER postgres WITH PASSWORD 'Root1.3456';

```
4. 退出psql
   
```shell
\q
```
5. 删除postgres的历史密码
   
```shell
   sudo passwd -d postgres
```
会提示:

```
Removing password for user postgres.
passwd: Success
```

6. 重新设置用户postgres的密码

```shell
sudo -u postgres passwd

```

会提示2次输入密码的提示，输入成功之后；

```
passwd: all authentication tokens updated successfully.

```

## PostgreSql之连接访问权限

postgresql.conf 文件
数据库集簇安装部署完成后，都要更改其中的监听地址，否则默认只监听数据库服务器本地地址，另外确保监听的端口号要通畅，不被防火墙或其他网络安全策略所限制。

1. 查询路径；
```shell
sudo -u postgres psql

SHOW config_file;
```

返回

```
 config_file
----------------------------------------
 /var/lib/pgsql/15/data/postgresql.conf
(1 row)
```


   
