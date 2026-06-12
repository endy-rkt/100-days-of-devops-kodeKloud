# Day 11:  Install and Configure Tomcat Server

**Subject:**

The `Nautilus` 
application development team recently finished the beta version of one 
of their Java-based applications, which they are planning to deploy on 
one of the app servers in `Stratos DC`. After an internal team meeting, they have decided to use the `tomcat` application server. Based on the requirements mentioned below complete the task:

a.  Install `tomcat` server on `App Server 1`.

b. Configure it to run on port `8083`.

c. There is a `ROOT.war` file on `Jump host` at location `/tmp`.

Deploy it on this tomcat server and make sure the webpage works directly on base URL i.e `curl http://stapp01:8083`

---

**Solution:**

Tomcat is a Java application server designed to deploy [Java Servlets](https://www.digitalocean.com/community/tutorials/servlet-tutorial-java) and [JSPs](https://www.digitalocean.com/community/tutorials/servlet-jsp-tutorial) on your system. 

- setup java environment (jdk)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%201.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%202.png)

- set up a tomcat user

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%203.png)

It is not advisable to run Tomcat under a root account. Hence we need to create a new user where we run the Tomcat server on our system. 

- download the tomcat package at https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.115/bin/apache-tomcat-9.0.115.tar.gz

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%204.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%205.png)

- change the permission and ownership to tomcat user

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%206.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%207.png)

- create a tomcat service

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%208.png)

search for JAVA_HOME

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%209.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2010.png)

- start the service

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2011.png)

- verify

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2012.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2013.png)

- change the port

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2014.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2015.png)

- change name

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2016.png)

- move the ROOT.war

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2017.png)

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2018.png)

- deploy the site

![image.png](Day%2011%20Install%20and%20Configure%20Tomcat%20Server/image%2019.png)