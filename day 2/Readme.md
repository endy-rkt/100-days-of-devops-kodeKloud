# Day 2: Temporary User Setup with Expiry

**Subject:**

As part of the temporary assignment to the `Nautilus` project, a developer named `mark`
 requires access for a limited duration. To ensure smooth access 
management, a temporary user account with an expiry date is needed. 
Here's what you need to do:

Create a user named `mark` on `App Server 3` in Stratos Datacenter. Set the expiry date to `2026-12-07`, ensuring the user is created in lowercase as per standard protocol.

> Note: You can find the infrastructure details by clicking on the **Details of all Users and Servers** button on the top-right section of the page.
> 

---

**Solution:**

- We need fist to navigate into the `App Server 3` . For that we ll need the credential to ssh in this server.

![image.png](Day%202%20Temporary%20User%20Setup%20with%20Expiry/image.png)

- SSH into the `App Server 3` then we can create our user.

![image.png](Day%202%20Temporary%20User%20Setup%20with%20Expiry/image%201.png)

![image.png](Day%202%20Temporary%20User%20Setup%20with%20Expiry/image%202.png)

- Then we create our user.

![image.png](Day%202%20Temporary%20User%20Setup%20with%20Expiry/image%203.png)

> we can use the -e, --expiredate EXPIRE_DATE to sets the date on which the user account will be disabled.
>
