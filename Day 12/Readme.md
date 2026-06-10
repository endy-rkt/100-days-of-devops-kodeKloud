# Day 12:  Linux Network Services

**Subject:**

Our monitoring tool has reported an issue in `Stratos Datacenter`. One of our app servers has an issue, as its Apache service is not reachable on port `8087`
 (which is the Apache port). The service itself could be down, the 
firewall could be at fault, or something else could be causing the 
issue.

Use tools like `telnet`, `netstat`, etc. to 
find and fix the issue. Also make sure Apache is reachable from the jump
 host without compromising any security settings.

Once fixed, you can test the same using command `curl http://stapp03:8087` command from jump host.

`Note:` Please do not try to alter the existing `index.html` code, as it will lead to task failure.

---

**Solution:**

- Check the server who has problem

![image.png](Day%2012%20Linux%20Network%20Services/image.png)

so here it’s app1

- check there is a server that listen on the port

![image.png](Day%2012%20Linux%20Network%20Services/image%201.png)

here we see that the port listen on local address

- check what service is listen on it

![image.png](Day%2012%20Linux%20Network%20Services/image%202.png)

so it’s not apache and we need to repair this

- fix the sendmail port

![image.png](Day%2012%20Linux%20Network%20Services/image%203.png)

![image.png](Day%2012%20Linux%20Network%20Services/image%204.png)

- check the problem in apache

![image.png](Day%2012%20Linux%20Network%20Services/image%205.png)

- fix this servername error and the listen socket

![image.png](Day%2012%20Linux%20Network%20Services/image%206.png)

- check it

![image.png](Day%2012%20Linux%20Network%20Services/image%207.png)

- verify firewall

![image.png](Day%2012%20Linux%20Network%20Services/image%208.png)

- add rules to allow the port

 

![image.png](Day%2012%20Linux%20Network%20Services/image%209.png)

In iptables, rules are processed from top to bottom. Once a packet hits that REJECT line, it’s blocked immediately, and the rules below it (like your port 8087 rule) are never checked. To fix this, you need to insert the rule at the top of the chain rather than appending it to the end.

- test

 

![image.png](Day%2012%20Linux%20Network%20Services/image%2010.png)