# Day 15:  Setup SSL for Nginx

**Subject:**

The system admins team of `xFusionCorp Industries` needs to deploy a new application on `App Server 2` in `Stratos Datacenter`.
 They have some pre-requites to get ready that server for application 
deployment. Prepare the server as per requirements shared below:

1. Install and configure `nginx` on `App Server 2`.

2. On `App Server 2` there is a self signed SSL certificate and key present at location `/tmp/nautilus.crt` and `/tmp/nautilus.key`. Move them to some appropriate location and deploy the same in Nginx.

3. Create an `index.html` file with content `Welcome!` under Nginx document root.

4. For final testing try to access the `App Server 2` link (via hostname) from `jump host` using curl command. For example: `curl -Ik https://<app-server-name>/`.

---

**Solution:**

- install nginx

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image.png)

- move key to these location

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%201.png)

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%202.png)

- create index.html

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%203.png)

- customize the nginx.conf

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%204.png)

- launch it

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%205.png)

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%206.png)

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%207.png)

- test

![image.png](Day%2015%20Setup%20SSL%20for%20Nginx/image%208.png)