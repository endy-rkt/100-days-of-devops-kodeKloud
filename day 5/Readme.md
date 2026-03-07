# Day 5: SElinux Installation and Configuration

**Subject:**

Following a security audit, the 
xFusionCorp Industries security team has opted to enhance application 
and server security with SELinux. To initiate testing, the following 
requirements have been established for `App server 2` in the `Stratos Datacenter:`

1. Install the required `SELinux` packages.
2. Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.
3. No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.
4. Disregard the current status of SELinux via the command line; the final status after the reboot should be `disabled`.

---

**Solution:**

- Navigate to `App server 2`
- Install selinux packages

![image.png](Day%205%20SElinux%20Installation%20and%20Configuration/image.png)

- Disable selinux

![image.png](Day%205%20SElinux%20Installation%20and%20Configuration/image%201.png)

- check it

![image.png](Day%205%20SElinux%20Installation%20and%20Configuration/image%202.png)