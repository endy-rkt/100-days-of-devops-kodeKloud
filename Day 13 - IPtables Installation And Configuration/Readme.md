# Day 13:  IPtables Installation And Configuration

**Subject:**

We have one of our websites up and running on our `Nautilus` infrastructure in `Stratos DC`. Our security team has raised a concern that right now Apache’s port i.e `3000`
 is open for all since there is no firewall installed on these hosts. So
 we have decided to add some security layer for these hosts and after 
discussions and recommendations we have come up with the following 
requirements:

1. Install `iptables` and all its dependencies on each app host.

2. Block incoming port `3000` on all apps for everyone except for LBR host.

3. Make sure the rules remain, even after system reboot.

---

**Solution:**

https://www.hostinger.com/tutorials/iptables-tutorial

- Install iptables

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image.png)

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%201.png)

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%202.png)

- check LBR host address

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%203.png)

- create rules to allow LBR

 

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%204.png)

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%205.png)

- make it persistent

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%206.png)

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%207.png)

make sure to add the rules to number 1

![image.png](Day%2013%20IPtables%20Installation%20And%20Configuration/image%208.png)

sudo iptables -I INPUT 1 -p tcp --dport 3001 -j ACCEPT