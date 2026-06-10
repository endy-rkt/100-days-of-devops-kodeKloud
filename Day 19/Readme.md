# Day 19:   Install and Configure Web Application

**Subject:**

xFusionCorp Industries is planning to host two static websites on their infra in `Stratos Datacenter`. The development of these websites is still in-progress, but we want to get the servers ready. Please perform the following steps to accomplish the task:

a. Install `httpd` package and dependencies on `app server 1`.

b. Apache should serve on port `8087`.

c. There are two website's backups `/home/thor/official` and `/home/thor/games` on `jump_host`. Set them up on Apache in a way that `official` should work on the link `http://localhost:8087/official/` and `games` should work on link `http://localhost:8087/games/` on the mentioned app server.

d. Once configured you should be able to access the website using `curl` command on the respective app server, i.e `curl http://localhost:8087/official/` and `curl http://localhost:8087/games/`

---

**Solution:**

https://oneuptime.com/blog/post/2026-03-04-install-configure-apache-httpd-rhel-9/view

https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/8/html/deploying_different_types_of_servers/setting-apache-http-server_deploying-different-types-of-servers

- install httpd

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image.png)

- confirm version

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%201.png)

- copy file into the server

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%202.png)

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%203.png)

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%204.png)

- configure conf

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%205.png)

in /etc/httpd/conf/httpd.conf

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%206.png)

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%207.png)

- set permission and test it

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%208.png)

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%209.png)

```
# Alias for the /official location
Alias /official "/var/www/html/official"
<Directory "/var/www/html/official">
    Options Indexes FollowSymLinks
    AllowOverride None
    Require all granted
</Directory>
```

- verify

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%2010.png)

![image.png](Day%2019%20Install%20and%20Configure%20Web%20Application/image%2011.png)