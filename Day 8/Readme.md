# Day 8:  Install Ansible

**Subject:**

During the weekly meeting, the Nautilus DevOps team discussed about the automation and configuration management solutions that they want to implement. While considering several options, the team has decided to go with `Ansible` for now due to its simple setup and minimal pre-requisites. The team wanted to start testing using Ansible, so they have decided to use `jump host` as an Ansible controller to test different kind of tasks on rest of the servers.

Install `ansible` version `4.9.0` on `Jump host` using `pip3` only. Make sure Ansible binary is available globally on this system, i.e all users on this system are able to run Ansible commands.

---

**Solution:**

- **What is ansible?**
    
    https://docs.ansible.com/projects/ansible/latest/installation_guide/intro_installation.html
    
    **Ansible** is an **open-source automation tool** used to **configure servers, deploy applications, and manage infrastructure automatically**. It is widely used in **DevOps** and **system administration**.
    
    Instead of manually logging into servers and running commands, you write **automation scripts (called playbooks)** and Ansible executes them on many machines.
    
    Key characteristics:
    
    - **Agentless** → no software needed on the managed servers (uses SSH).
    - **Declarative** → you describe the desired state (e.g., “nginx must be installed”).
    - **Infrastructure as Code (IaC)** → infrastructure configuration stored in code.
    
    ---
    
    # Core Concepts
    
    ### 1. Control Node
    
    The machine where **Ansible is installed and executed**.
    
    ### 2. Managed Nodes
    
    Servers controlled by Ansible (Linux, cloud instances, containers, etc.).
    
    ### 3. Inventory
    
    List of servers Ansible manages.
    
    Example:
    
    ```
    [webservers]
    192.168.1.10
    192.168.1.11
    
    [db]
    192.168.1.20
    ```
    
    ### 4. Playbooks
    
    Automation scripts written in **YAML**.
    
    Example:
    
    ```yaml
    - hosts: webservers
      become: yes
      tasks:
        - name: install nginx
          apt:
            name: nginx
            state: present
    ```
    
    This means:
    
    - connect to `webservers`
    - install **nginx**
    
    ---
    
    # Example Uses of Ansible
    
    ## 1. Automatic Server Configuration
    
    Instead of manually configuring a server.
    
    Example:
    
    ```yaml
    - hosts: servers
      tasks:
        - name: install git
          apt:
            name: git
            state: present
    ```
    
    Use cases:
    
    - install packages
    - configure users
    - manage SSH keys
    - setup firewall
    
    ---
    
    # 2. Application Deployment
    
    Example: Deploy a **Node.js API**.
    
    ```yaml
    - hosts: web
      tasks:
        - name: pull project
          git:
            repo: https://github.com/app/api.git
            dest: /var/www/api
    
        - name: install dependencies
          npm:
            path: /var/www/api
    ```
    
    This can deploy an app to **10+ servers automatically**.
    
    ---
    
    # 3. Docker Infrastructure Setup
    
    Example:
    
    ```yaml
    - hosts: docker_servers
      tasks:
        - name: install docker
          apt:
            name: docker.io
            state: present
    ```
    
    Then run containers automatically.
    
    ---
    
    # 4. Cloud Infrastructure Provisioning
    
    Ansible can create resources in:
    
    - **Amazon Web Services**
    - **Google Cloud Platform**
    - **Microsoft Azure**
    
    Example tasks:
    
    - create EC2 instances
    - configure networking
    - deploy apps
    
    ---
    
    # 5. CI/CD Automation
    
    Ansible is often used with tools like:
    
    - **Jenkins**
    - **GitLab CI**
    
    Example workflow:
    
    ```
    push code → CI pipeline → Ansible deploys servers
    ```
    
    ---
    
    # 6. Managing Hundreds of Servers
    
    Example command:
    
    ```bash
    ansible all -m ping
    ```
    
    This checks if **all servers are reachable**.
    
    Output:
    
    ```
    server1 | SUCCESS
    server2 | SUCCESS
    server3 | SUCCESS
    ```
    
    ---
    
    # 7. Kubernetes Cluster Setup
    
    You can automate installing Kubernetes tools like:
    
    - **Kubernetes**
    - **Docker**
    
    Many production clusters are built with Ansible.
    
    ---
    
    # Example Real Scenario
    
    Imagine you have **10 servers**.
    
    Without Ansible:
    
    ```
    ssh server1
    install nginx
    
    ssh server2
    install nginx
    
    ssh server3
    install nginx
    ...
    ```
    
    With Ansible:
    
    ```
    ansible-playbook setup-nginx.yml
    ```
    
    Done in **seconds**.
    
    ---
    
    # When Developers Use Ansible
    
    Common cases:
    
    - DevOps automation
    - server provisioning
    - infrastructure as code
    - cloud deployment
    - CI/CD pipelines
    - Kubernetes cluster setup
    
    ---
    
    ✅ **Simple summary**
    
    Ansible = **automating infrastructure and server tasks using code**
    
    Instead of:
    
    ```
    manual server configuration
    ```
    
    You do:
    
    ```
    infrastructure as code
    ```
    
    ---
    
    If you want, I can also show you:
    
    - **How Ansible works with Docker + microservices** (very useful for your project)
    - **A real DevOps architecture using Ansible + Kubernetes + CI/CD**
    - **Ansible vs Terraform vs Kubernetes (very important difference)**.
- install ansible

![image.png](Day%208%20Install%20Ansible/image.png)

- check version

![image.png](Day%208%20Install%20Ansible/image%201.png)