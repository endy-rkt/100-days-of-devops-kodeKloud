# Day 5: SElinux Installation and Configuration

**Subject:**

Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. To initiate testing, the following  requirements have been established for `App server 2` in the `Stratos Datacenter:`

1. Install the required `SELinux` packages.
2. Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.
3. No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.
4. Disregard the current status of SELinux via the command line; the final status after the reboot should be `disabled`.

---

**Solution:**

First let’s what is SELinux.

- **what is SELinux?**
    
    https://www.redhat.com/en/topics/linux/what-is-selinux
    
    ### What is SELinux?
    
    Security-Enhanced Linux (SELinux) is a [security](https://www.redhat.com/en/topics/security) architecture for [Linux® systems](https://www.redhat.com/en/topics/linux/what-is-linux) that allows administrators to have more control over who can access the system. It was originally developed by the United States National Security Agency (NSA) as a series of [patches](https://www.redhat.com/en/topics/linux/what-is-linux-kernel-live-patching) to the [Linux kernel](https://www.redhat.com/en/topics/linux/what-is-the-linux-kernel) using Linux Security Modules (LSM).
    
    ### How does SELinux work?
    
    SELinux defines access controls for the applications, processes, and files on a system. It uses security policies, which are a set of rules that tell SELinux what can or can’t be accessed, to enforce the access allowed by policy.
    
    When an application or process, known as a subject, makes a request to access an object, like a file, SELinux checks with an access vector cache (AVC), where permissions are cached for subjects and objects.
    
    If SELinux is unable to make a decision about access  based on the cached permissions, it sends the request to the security server. The security server checks for the security context of the app or process and the file. Security context is applied from the SELinux policy database. Permission is then granted or denied.
    
    If permission is denied, an "avc: denied" message will be available in /var/log.messages.
    
- **why SELinux?**
    
    # 1. Normal Linux permissions (without SELinux)
    
    Linux already has a security model using:
    
    - **Users**
    - **Groups**
    - **File permissions**
    
    Example:
    
    ```
    -rw-r----- 1 alice dev file.txt
    ```
    
    Meaning:
    
    - owner (alice): read/write
    - group (dev): read
    - others: nothing
    
    Applications run **as a user**, so they inherit that user's permissions.
    
    Example:
    
    If a program runs as user `bob`, it can only access files that `bob` is allowed to access.
    
    So **even without SELinux**, applications cannot access everything.
    
    ---
    
    # 2. The problem with only Linux permissions
    
    Traditional permissions are **too simple**.
    
    They only answer:
    
    > "Is this user allowed to read/write/execute this file?"
    > 
    
    But they **do not restrict what programs can do** once they run.
    
    Example:
    
    Suppose a web server runs as user `www-data`.
    
    If the web server gets hacked, the attacker can:
    
    - read **any file accessible to www-data**
    - modify anything writable by `www-data`
    - open network connections
    - run other programs
    
    Linux permissions cannot say things like:
    
    ❌ "Apache can read web files but cannot read `/etc/shadow`."
    
    If Apache runs as root (bad configuration), it could read **everything**.
    
    ---
    
    # 3. What SELinux adds
    
    **SELinux = Security Enhanced Linux**
    
    It adds **Mandatory Access Control (MAC)**.
    
    Instead of just:
    
    ```
    user -> file
    ```
    
    SELinux also checks:
    
    ```
    process type -> file type
    ```
    
    So even if Linux permissions say **allowed**, SELinux can say **DENIED**.
    
    ---
    
    # 4. Example with SELinux
    
    Suppose Apache tries to read `/etc/shadow`.
    
    Linux permissions might allow it (if root).
    
    But SELinux policy says:
    
    ```
    httpd_t process
    cannot read
    shadow_t file
    ```
    
    So the kernel blocks it.
    
    Result:
    
    ```
    Permission denied
    ```
    
    even for root.
    
    ---
    
    # 5. SELinux labels everything
    
    SELinux labels:
    
    - files
    - processes
    - sockets
    - ports
    
    Example:
    
    ```
    /var/www/index.html   -> httpd_sys_content_t
    /etc/shadow           -> shadow_t
    Apache process        -> httpd_t
    ```
    
    Policy rules define:
    
    ```
    httpd_t  -> can read  httpd_sys_content_t
    httpd_t  -> cannot read shadow_t
    ```
    
    So Apache can only read **web files**, not system secrets.
    
    ---
    
    # 6. Why this is powerful
    
    If a service gets hacked:
    
    Without SELinux:
    
    ```
    attacker -> full user privileges
    ```
    
    With SELinux:
    
    ```
    attacker -> limited to that service's sandbox
    ```
    
    Example:
    
    Compromised nginx cannot:
    
    - read SSH keys
    - modify system binaries
    - access database files
    - read `/etc/shadow`
    
    ---
    
    # 7. Simple analogy
    
    Think of **Linux permissions** like:
    
    > House key (you can enter the house).
    > 
    
    But **SELinux** is like:
    
    > Rooms with special locks inside the house.
    > 
    
    Even if you are inside the house, you **cannot enter every room**.
    
    ---
    
    # 8. Why people disable SELinux
    
    Because it can break applications if policies are wrong.
    
    Typical errors:
    
    ```
    SELinux is preventing /usr/sbin/httpd from reading file...
    ```
    
    Admins sometimes disable it instead of fixing policies.
    
    ---
    
    # 9. Where SELinux is used
    
    Common in:
    
    - Red Hat Enterprise Linux
    - CentOS
    - Fedora
    - Android
    
    Android uses SELinux heavily to isolate apps.
    
    ---
    
    # 10. Short summary
    
    Without SELinux:
    
    ```
    user -> file permissions
    ```
    
    With SELinux:
    
    ```
    user -> file permissions
    +
    process -> security policy
    ```
    
    SELinux can **override normal permissions** to protect the system.
    
- **AppArmor vs SELinux**
    
    **AppArmor** is another Linux security system similar to **SELinux**.
    
    Both try to **restrict what programs are allowed to do**, even if the program is running as root.
    
    The main idea:
    
    > **AppArmor confines programs to a limited set of actions using security profiles.**
    > 
    
    ---
    
    # 1. What AppArmor does
    
    With normal Linux permissions:
    
    ```
    user → file permissions
    ```
    
    With AppArmor:
    
    ```
    program → allowed resources
    ```
    
    So AppArmor says things like:
    
    - this program **can read these files**
    - this program **cannot access this directory**
    - this program **cannot open network connections**
    - this program **cannot execute other programs**
    
    Even if the program is exploited.
    
    ---
    
    # 2. Example
    
    Suppose a web server runs:
    
    - Nginx
    
    AppArmor profile might say:
    
    ```
    /usr/sbin/nginx {
      /var/www/** r,
      /var/log/nginx/** rw,
      /etc/nginx/** r,
    }
    ```
    
    Meaning:
    
    Allowed:
    
    - read `/var/www`
    - read nginx config
    - write logs
    
    Denied:
    
    - `/etc/shadow`
    - `/home/*`
    - `/root`
    - random binaries
    
    So if nginx is hacked, the attacker is **confined inside the profile**.
    
    ---
    
    # 3. Where AppArmor is used
    
    It is the default security system in:
    
    - Ubuntu
    - Debian
    
    It is also used by:
    
    - Docker
    - Snap
    
    ---
    
    # 4. AppArmor vs SELinux (important difference)
    
    The biggest difference is **how they define policies**.
    
    ### SELinux → label-based
    
    SELinux uses **security labels**.
    
    Example:
    
    ```
    httpd_t → process type
    shadow_t → file type
    ```
    
    Policy says:
    
    ```
    httpd_t cannot read shadow_t
    ```
    
    So access control depends on **labels attached to objects**.
    
    ---
    
    ### AppArmor → path-based
    
    AppArmor uses **file paths**.
    
    Example:
    
    ```
    deny /etc/shadow r
    allow /var/www/** r
    ```
    
    So rules are simpler and easier to understand.
    
    ---
    
    # 5. Why many admins prefer AppArmor
    
    Because it is **much easier to configure**.
    
    Example AppArmor rule:
    
    ```
    /home/** r
    ```
    
    Very easy.
    
    SELinux equivalent often requires complex policies.
    
    That’s why many people disable SELinux but keep AppArmor.
    
    ---
    
    # 6. Security difference
    
    Security researchers usually say:
    
    **SELinux is stronger but more complex.**
    
    **AppArmor is easier but slightly less powerful.**
    
    Why?
    
    Because path-based controls can sometimes be bypassed using tricks like:
    
    - symlinks
    - mount tricks
    - path confusion
    
    Label-based systems (SELinux) are harder to bypass.
    
    ---
    
    # 7. Simple comparison
    
    | Feature | SELinux | AppArmor |
    | --- | --- | --- |
    | Policy type | Label-based | Path-based |
    | Complexity | Hard | Easy |
    | Security strength | Very strong | Strong |
    | Default in | RHEL / Fedora | Ubuntu / Debian |
    
    ---
    
    # 8. Simple mental model
    
    Think of them like sandboxes.
    
    SELinux sandbox:
    
    ```
    based on object labels
    ```
    
    AppArmor sandbox:
    
    ```
    based on file paths
    ```
    
    Both try to stop attackers **after an exploit**.
    
    ---
    
    ✅ **Short summary**
    
    AppArmor is a Linux security system that:
    
    - restricts what programs can do
    - protects the system if a service is hacked
    - uses simple **path-based profiles**
    - is easier to configure than SELinux
    

- Navigate to `App server 2`
- Install selinux packages

![image.png](Day%205%20SElinux%20Installation%20and%20Configuration/image.png)

- Disable selinux

![image.png](Day%205%20SElinux%20Installation%20and%20Configuration/image%201.png)

- check it

![image.png](Day%205%20SElinux%20Installation%20and%20Configuration/image%202.png)