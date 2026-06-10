# Day 16:  Install and Configure Nginx as an LBR

**Subject:**

Day by day traffic is increasing on one of the websites managed by the `Nautilus`
 production support team. Therefore, the team has observed a degradation
 in website performance. Following discussions about this issue, the 
team has decided to deploy this application on a high availability stack
 i.e on `Nautilus` infra in `Stratos DC`. They 
started the migration last month and it is almost done, as only the LBR 
server configuration is pending. Configure LBR server as per the 
information given below:

a. Install `nginx` on the `LBR` (load balancer) server if it is not already installed.

b. Configure load-balancing with the `http` context making use of all `App Servers`. Ensure that you update only the main Nginx configuration file located at `/etc/nginx/nginx.conf`.

c. Make sure you do not update the apache port that is already 
defined in the apache configuration on all app servers, also make sure 
apache service is up and running on all the app servers.

d. Once done, you can access the website by running `curl http://stlb01:80` in the terminal.

---

**Solution:**

https://www.getpagespeed.com/server-setup/nginx/nginx-load-balancing

- check that all app servers are up

![image.png](Day%2016%20Install%20and%20Configure%20Nginx%20as%20an%20LBR/image.png)

![image.png](Day%2016%20Install%20and%20Configure%20Nginx%20as%20an%20LBR/image%201.png)

- check if nginx is installed on the LBR

![image.png](Day%2016%20Install%20and%20Configure%20Nginx%20as%20an%20LBR/image%202.png)

The nginx is presented but not up

- configure nginx

Take the ip of app server first

app3: 10.244.164.12

app2: 10.244.73.150

app1: 10.244.195.61

![image.png](Day%2016%20Install%20and%20Configure%20Nginx%20as%20an%20LBR/image%203.png)

![image.png](Day%2016%20Install%20and%20Configure%20Nginx%20as%20an%20LBR/image%204.png)

- start it

![image.png](Day%2016%20Install%20and%20Configure%20Nginx%20as%20an%20LBR/image%205.png)

![image.png](Day%2016%20Install%20and%20Configure%20Nginx%20as%20an%20LBR/image%206.png)