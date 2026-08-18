# Day 91:  Ansible Lineinfile Module

**subject**

***

The Nautilus DevOps team want to install and set up a simple`httpd`web server on all app servers in`Stratos DC`. They also want to deploy a sample web page using Ansible. Therefore, write the required playbook to complete this task as per details mentioned below.
We already have an`inventory`file under`/home/thor/ansible`directory on`jump host`. Write a playbook`playbook.yml`under`/home/thor/ansible`directory on`jump host`itself. Using the playbook perform below given tasks:

Install`httpd`web server on all app servers, and make sure its service is up and running.

Create a file`/var/www/html/index.html`with content:

`This is a Nautilus sample file, created using Ansible!`

Using`lineinfile`Ansible module add some more content in`/var/www/html/index.html`file. Below is the content:

`Welcome to Nautilus Group!`

Also make sure this new line is added at the top of the file.

The`/var/www/html/index.html`file's user and group`owner`should be`apache`on all app servers.

The`/var/www/html/index.html`file's permissions should be`0744`on all app servers.

`Note:`Validation will try to run the playbook using command`ansible-playbook -i inventory playbook.yml`so please make sure the playbook works this way without passing any extra arguments.

***

https://blog.stephane-robert.info/docs/infra-as-code/gestion-de-configuration/ansible/modules/fichiers/module-copy/

https://docs.ansible.com/projects/ansible/latest/collections/ansible/builtin/lineinfile\_module.html

* Check the current work

![](assets/EPskX7Wg_0sEQh63HxYhkWi97DLKa_ldpphABA_If9I=.png)

* Create the playbook

![](assets/dFeUGuE_E22EBCheTQpfaurkb6SrlIKp7NlJ6WG-et8=.png)

* Run and check

![](assets/k-6oZAHVFyf3wpEgJBpt3nPPyBHmlPWEPfjGSSpniz0=.png)
