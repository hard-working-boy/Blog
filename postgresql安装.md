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

