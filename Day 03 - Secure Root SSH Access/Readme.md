# Day 3: Secure Root SSH Access

**Subject:**

Following security audits, the `xFusionCorp Industries` security team has rolled out new protocols, including the restriction of direct root SSH login.

Your task is to disable direct SSH root login on all app servers within the `Stratos Datacenter`.

---

**Solution:**

We need fist to navigate into each server and edit  SSH configuration

![image.png](Day%203%20Secure%20Root%20SSH%20Access/image.png)

- Edit the SSH configuration in /etc/ssh/sshd_configuration and change the PermitRootLogin to no

![image.png](Day%203%20Secure%20Root%20SSH%20Access/image%201.png)

- Restart the ssh service

![image.png](Day%203%20Secure%20Root%20SSH%20Access/image%202.png)