# Day 20:   Configure Nginx + PHP-FPM Using Unix Sock

**Subject:**

The `Nautilus` application development team is planning to launch a new PHP-based application, which they want to deploy on `Nautilus` infra in `Stratos DC`. The development team had a meeting with the production support team and they have shared some requirements regarding the infrastructure. Below are the requirements they shared:

a. Install `nginx` on `app server 1` , configure it to use port `8098` and its document root should be `/var/www/html`.

b. Install `php-fpm` version `8.1` on `app server 1`, it must use the unix socket `/var/run/php-fpm/default.sock` (create the parent directories if don't exist).

c. Configure php-fpm and nginx to work together.

d. Once configured correctly, you can test the website using `curl http://stapp01:8098/index.php` command from jump host.

NOTE: We have copied two files, `index.php` and `info.php`, under `/var/www/html` as part of the `PHP-based application` setup. Please do not modify these files.

---

**Solution:**

- install nginx and configure it

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image.png)

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%201.png)

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%202.png)

- install php

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%203.png)

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%204.png)

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%205.png)

- config and test

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%206.png)

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%207.png)

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%208.png)

- configure nginx

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%209.png)

- test it

![image.png](Day%2020%20Configure%20Nginx%20+%20PHP-FPM%20Using%20Unix%20Sock/image%2010.png)