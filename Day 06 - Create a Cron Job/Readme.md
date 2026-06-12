# Day 6: Create a Cron Job

**Subject:**

The `Nautilus` system
 admins team has prepared scripts to automate several day-to-day tasks. 
They want them to be deployed on all app servers in `Stratos DC`
 on a set schedule. Before that they need to test similar functionality 
with a sample cron job. Therefore, perform the steps below:

a. Install `cronie` package on all `Nautilus` app servers and start `crond` service.

b. Add a cron `*/5 * * * * echo hello > /tmp/cron_text` for `root` user.

---

**Solution:**

**`cron`** is a time-based [job scheduler](https://en.wikipedia.org/wiki/Job_scheduler). A scheduled job is known as a *cron job*.[[1]](https://en.wikipedia.org/wiki/Cron#cite_note-1)[[2]](https://en.wikipedia.org/wiki/Cron#cite_note-2)[[3]](https://en.wikipedia.org/wiki/Cron#cite_note-3)[[4]](https://en.wikipedia.org/wiki/Cron#cite_note-4) Although typically used to automate system maintenance and administration it can be used to automate any task. 

- Install cronie

![image.png](Day%206%20Create%20a%20Cron%20Job/image.png)

- start and enable crond

![image.png](Day%206%20Create%20a%20Cron%20Job/image%201.png)

- create cron job

![image.png](Day%206%20Create%20a%20Cron%20Job/image%202.png)

![image.png](Day%206%20Create%20a%20Cron%20Job/image%203.png)

![image.png](Day%206%20Create%20a%20Cron%20Job/image%204.png)