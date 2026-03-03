# Day 1: Linux User Setup with Non-Interactive Shell

**Subject:**

To accommodate the backup agent tool's specifications, the system admin team at `xFusionCorp Industries` requires the creation of a user with a non-interactive shell. Here's your task:

Create a user named `john` with a non-interactive shell on `App Server 1`.

> Note: You can find the infrastructure details by clicking on the **Details of all Users and Servers** button on the top-right section of the page.
> 

---

**Solution:**

- We need fist to navigate into the `App Server 1` . For that we ll need the credential to ssh in this server.

![image.png](Day%201%20Linux%20User%20Setup%20with%20Non-Interactive%20Shell/image.png)

- SSH into the `App Server 1` then we can create our user.

![image.png](Day%201%20Linux%20User%20Setup%20with%20Non-Interactive%20Shell/image%201.png)

- View what authorization and privilege, we have.

![image.png](Day%201%20Linux%20User%20Setup%20with%20Non-Interactive%20Shell/image%202.png)

- Then we create our user.

![image.png](Day%201%20Linux%20User%20Setup%20with%20Non-Interactive%20Shell/image%203.png)

> we can use the -s, --shell SHELL to sets the path to the user's login shell.
>