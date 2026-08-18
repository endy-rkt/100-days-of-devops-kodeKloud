# Day 93:  Using Ansible Conditionals

**subject**

***

The Nautilus DevOps team had a discussion about, how they can train different team members to use Ansible for different automation tasks. There are numerous ways to perform a particular task using Ansible, but we want to utilize each aspect that Ansible offers. The team wants to utilise Ansible's conditionals to perform the following task:





An`inventory`file is already placed under`/home/thor/ansible`directory on`jump host`, with all the`Stratos DC app servers`included.





Create a playbook`/home/thor/ansible/playbook.yml`and make sure to use Ansible's`when`conditionals statements to perform the below given tasks.

1. Copy`blog.txt`file present under`/usr/src/data`directory on`jump host`to`App Server 1`under`/opt/data`directory. Its user and group owner must be user`tony`and its permissions must be`0755`.


2. Copy`story.txt`file present under`/usr/src/data`directory on`jump host`to`App Server 2`under`/opt/data`directory. Its user and group owner must be user`steve`and its permissions must be`0755`.


3. Copy`media.txt`file present under`/usr/src/data`directory on`jump host`to`App Server 3`under`/opt/data`directory. Its user and group owner must be user`banner`and its permissions must be`0755`.



`NOTE:`You can use`ansible_nodename`variable from gathered facts with`when`condition. Additionally, please make sure you are running the play for all hosts i.e use`- hosts: all`.





`Note:`Validation will try to run the playbook using command`ansible-playbook -i inventory playbook.yml`, so please make sure the playbook works this way without passing any extra arguments.

***

https://blog.stephane-robert.info/docs/infra-as-code/gestion-de-configuration/ansible/ecrire-code/controle-flux/conditions-when/

https://docs.ansible.com/projects/ansible/latest/playbook\_guide/playbooks\_conditionals.html

* Check current work

![](assets/XzFP4YtvfNMIe-6TuBl10_shssmwZCNqQmABVFSheb8=.png)

* Create the playbook

![](assets/HJQkPQFaj-R5Q0Cq6yXh_L-e_VsCllWILYbBWZ3Vu-M=.png)

* Run and check

![](assets/RbCcFajDd5VzsPn5Seriq2mKcnOPdLb3MjPpYoHs_UY=.png)
