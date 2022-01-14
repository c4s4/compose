# PostgreSQL

To create database and user, run the database shell and type:

```sql
CREATE DATABASE test;
CREATE USER test WITH ENCRYPTED PASSWORD 'test';
GRANT ALL PRIVILEGES ON DATABASE test TO test;
```
