# PostgreSQL

To create database and user, run the database shell and type:

```
postgres=# create database test;
postgres=# create user test with encrypted password 'test';
postgres=# grant all privileges on database test to test;
```
