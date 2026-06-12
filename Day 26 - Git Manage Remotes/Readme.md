# Day 26:   Git Manage Remotes

**Subject:**

The xFusionCorp development team added updates to the project that is maintained under `/opt/beta.git` repo and cloned under `/usr/src/kodekloudrepos/beta`. Recently some changes were made on Git server that is hosted on `Storage server` in `Stratos DC`. The DevOps team added some new Git remotes, so we need to update remote on `/usr/src/kodekloudrepos/beta` repository as per details mentioned below:

a.  In `/usr/src/kodekloudrepos/beta` repo add a new remote `dev_beta`  and point it to `/opt/xfusioncorp_beta.git` repository.

b. There is a file `/tmp/index.html` on same server; copy this file to the repo and add/commit to master branch.

c. Finally push `master` branch to this new remote origin.

---

**Solution:**

https://www.cloudbees.com/blog/git-remote-add

- add new remote origin

![image.png](Day%2026%20Git%20Manage%20Remotes/image.png)

- do operation

![image.png](Day%2026%20Git%20Manage%20Remotes/image%201.png)

- push to new remote

![image.png](Day%2026%20Git%20Manage%20Remotes/image%202.png)