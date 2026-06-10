# Day 17:  Install and Configure PostgreSQL

**Subject:**

The `Nautilus` application development team has shared that they are planning to deploy one newly developed application on `Nautilus` infra in `Stratos DC`.
 The application uses PostgreSQL database, so as a pre-requisite we need
 to set up PostgreSQL database server as per requirements shared below:

PostgreSQL database server is already installed on the `Nautilus` database server.

a. Create a database user `kodekloud_rin` and set its password to `B4zNgHA7Ya`.

b. Create a database `kodekloud_db5` and grant full permissions to user `kodekloud_rin` on this database.

`Note:` Please do not try to restart PostgreSQL server service.

---

**Solution:**

https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-20-04

https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e

- Check postgres is already running

![image.png](Day%2017%20Install%20and%20Configure%20PostgreSQL/image.png)

- Check version

![image.png](Day%2017%20Install%20and%20Configure%20PostgreSQL/image%201.png)

- Create user

![image.png](Day%2017%20Install%20and%20Configure%20PostgreSQL/image%202.png)

![image.png](Day%2017%20Install%20and%20Configure%20PostgreSQL/image%203.png)

- Create db and grant permission

![image.png](Day%2017%20Install%20and%20Configure%20PostgreSQL/image%204.png)

![image.png](Day%2017%20Install%20and%20Configure%20PostgreSQL/image%205.png)

- verify

![image.png](Day%2017%20Install%20and%20Configure%20PostgreSQL/image%206.png)