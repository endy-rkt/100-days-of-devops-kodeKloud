# Day 82: Create Ansible Inventory for App Server Testing

**subject**

***

The Nautilus DevOps team is testing Ansible playbooks on various servers within their stack. They've placed some playbooks under`/home/thor/playbook/`directory on the`jump host`and now intend to test them on`app server 1`in`Stratos DC`. However, an inventory file needs creation for Ansible to connect to the respective app. Here are the requirements:

a. Create an ini type Ansible inventory file`/home/thor/playbook/inventory`on`jump host`.





b. Include`App Server 1`in this inventory along with necessary variables for proper functionality.





c. Ensure the inventory hostname corresponds to the`server name`as per the wiki, for example`stapp01`for`app server 1`in`Stratos DC`.





`Note:`Validation will execute the playbook using the command`ansible-playbook -i inventory playbook.yml`. Ensure the playbook functions properly without any extra arguments.

***

https://blog.stephane-robert.info/docs/infra-as-code/gestion-de-configuration/ansible/premiers-pas/premier-inventaire/

https://docs.ansible.com/projects/ansible/latest/collections/ansible/builtin/ini\_inventory.html

* Check the current structure

![](assets/PMKFMeA8C_LSHqXdM9HaspmByIWpXZ0Dmt4Dc9YKuvs=.png)

* Create password less ssh

![](assets/sr0seQIXK9LqgLY1z4-6egKxfrxqaDmhv-e8ahC6GRo=.png)

* Create the playbook

ini version for the subject

![](assets/CGsKYUzlGA9ADnEEjBqx7Ev3NLMCnLFyoSvprZBTHi4=.png)

or

![](assets/APUBE2DeYZed_i0NTVNiL5L_UvylR9dDQLWuLBhWXiE=.png)

yaml version (we have failled with it thou)

![](assets/EZV_NZgMQZc7sFxyAqdb9N5ZYliT5rv-H1Rkk0EhJD8=.png)

* Test it

![](assets/9Jno_4qKb4QXFcpAirLwKQiwF52R5i_wP8PS38R6ov8=.png)

####
