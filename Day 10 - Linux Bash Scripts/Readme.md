# Day 10:  Linux Bash Scripts

**Subject:**

The production support team of `xFusionCorp Industries`
 is working on developing some bash scripts to automate different day to
 day tasks. One is to create a bash script for taking websites backup. 
They have a static website running on `App Server 2` in `Stratos Datacenter`, and they need to create a bash script named `ecommerce_backup.sh` which should accomplish the following tasks. (Also remember to place the script under `/scripts` directory on `App Server 2`).

a. Create a zip archive named `xfusioncorp_ecommerce.zip` of `/var/www/html/ecommerce` directory.

b. Save the archive in `/backup/` on `App Server 2`.
 This is a temporary storage, as backups from this location will be 
cleaned on a weekly basis. Therefore, we also need to save this backup 
archive on `Nautilus Storage Server`.

c. Copy the created archive to `Nautilus Storage Server` server in `/backup/` location.

d. Please make sure script won't ask for password while copying the 
archive file. Additionally, the respective server user (for example, `tony` in case of `App Server 1`) must be able to run it.

e. Do not use sudo inside the script.

**Note:**

The zip package must be installed on given App Server before executing 
the script. This package is essential for creating the zip archive of 
the website files. Install it manually outside the script.

---

**Solution:**

First let’s prepare our environment for the script.

- Install zip

![image.png](Day%2010%20Linux%20Bash%20Scripts/image.png)

- Set up a sshless connection so we can use scp copy

![image.png](Day%2010%20Linux%20Bash%20Scripts/image%201.png)

![image.png](Day%2010%20Linux%20Bash%20Scripts/image%202.png)

- check that we can use scp copy

![image.png](Day%2010%20Linux%20Bash%20Scripts/image%203.png)

- create the script

![image.png](Day%2010%20Linux%20Bash%20Scripts/image%204.png)

- adjust permission

![image.png](Day%2010%20Linux%20Bash%20Scripts/image%205.png)