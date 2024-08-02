# postgresql安装pgvector

1. 安装pgvector的extension
```shell
sudo yum install pgvector_15
```

2. 安装hstore等extension
```shell

 sudo yum install postgresql15-contrib
```

3.创建db时开启extension

```sql
CREATE EXTENSION IF NOT EXISTS vector;
CREATE EXTENSION IF NOT EXISTS hstore;
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

```
