# Day 7: Linux SSH Authentication

**Subject:**

The system admins team of `xFusionCorp Industries` has set up some scripts on `jump host` that run on regular intervals and perform operations on all app servers in `Stratos Datacenter`. To make these scripts work properly we need to make sure the `thor` user on jump host has password-less SSH access to all app servers through their respective sudo users (i.e `tony` for app server 1). Based on the requirements, perform the following:

Set up a password-less authentication from user `thor` on jump host to all app servers through their respective sudo users.

---

**Solution:**

https://medium.com/@prateek.malhotra004/streamlining-secure-remote-access-a-guide-to-passwordless-ssh-connections-between-linux-servers-8c26bb008af9

- we need to generate the key pair on the client machine

![image.png](Day%207%20Linux%20SSH%20Authentication/image.png)

- Copy the public key to the ssh server using `ssh-copy-id`

![image.png](Day%207%20Linux%20SSH%20Authentication/image%201.png)

- Test the ssh connection

![image.png](Day%207%20Linux%20SSH%20Authentication/image%202.png)

no authentification needed