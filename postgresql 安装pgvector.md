# postgresql安装pgvector

1. sudo yum install pgvector_15


2. 创建db时开启extension

```sql
CREATE EXTENSION IF NOT EXISTS vector;
CREATE EXTENSION IF NOT EXISTS hstore;
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

```
