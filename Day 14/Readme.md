# Day 14:  Linux Process Troubleshooting

**Subject:**

The production support team of 
xFusionCorp Industries has deployed some of the latest monitoring tools 
to keep an eye on every service, application, etc. running on the 
systems. One of the monitoring systems reported about Apache service 
unavailability on one of the app servers in `Stratos DC`.

Identify the faulty app host and fix the issue. Make sure Apache 
service is up and running on all app hosts. They might not have hosted 
any code yet on these servers, so you don't need to worry if Apache 
isn't serving any pages. Just make sure the service is up and running. 
Also, make sure Apache is running on port `3001` on all app servers.

---

**Solution:**

- check if the service is up

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image.png)

- check if what is using the port

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%201.png)

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%202.png)

- config sendmail to listen on other port

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%203.png)

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%204.png)

- start and configure apache

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%205.png)

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%206.png)

- Add firewall rules to allow traffic

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%207.png)

![image.png](Day%2014%20Linux%20Process%20Troubleshooting/image%208.png)