# Day 78: Jenkins Conditional Pipeline

**subject**

***

The development team of xFusionCorp Industries is working on to develop a new static website and they are planning to deploy the same on Nautilus App Server using Jenkins pipeline. They have shared their requirements with the DevOps team and accordingly we need to create a Jenkins pipeline job. Please find below more details about the task:

Click on the`Jenkins`button on the top bar to access the Jenkins UI. Login using username`admin`and password`Adm!n321`.





Similarly, click on the`Gitea`button on the top bar to access the Gitea UI. Login using username`sarah`and password`Sarah_pass123`. There under user`sarah`you will find a repository named`web_app`that is already cloned on**App Server 1**under`/var/www/html`. sarah is a developer who is working on this repository.





1. Add a slave node named`App Server 1`. It should be labeled as`stapp01`and its remote root directory should be`/home/sarah/jenkins_agent`(the repository is cloned under`/var/www/html`).


2. We have already cloned repository on**App Server 1**under`/var/www/html`.


3. Apache is already installed on the app server and is running on port`8080`.


4. Create a Jenkins pipeline job named`devops-webapp-job`(it must not be a`Multibranch pipeline`) and configure it to:


   * Add a string parameter named`BRANCH`.


   * It should conditionally deploy the code from`web_app`repository under`/var/www/html`on**App Server 1**, as this is the document root of the app server. The pipeline should have a single stage named`Deploy`( which is case sensitive ) to accomplish the deployment.


   * The pipeline should be conditional, if the value`master`is passed to the`BRANCH`parameter then it must deploy the`master`branch, on the other hand if the value`feature`is passed to the`BRANCH`parameter then it must deploy the`feature`branch.



LB server is already configured. You should be able to see the latest changes you made by clicking on the`App`button. Please make sure the required content is loading on the main URL`https://<LBR-URL>`i.e there should not be a sub-directory like`https://<LBR-URL>/web_app`etc.

`Note:`

1. You might need to install some plugins and restart Jenkins service. So, we recommend clicking on`Restart Jenkins when installation is complete and no jobs are running`on plugin installation/update page i.e`update centre`. Also, Jenkins UI sometimes gets stuck when Jenkins service restarts in the back end. In this case, please make sure to refresh the UI page.
2. For these kind of scenarios requiring changes to be done in a web UI, please take screenshots so that you can share it with us for review in case your task is marked incomplete. You may also consider using a screen recording software such as loom.com to record and share your work.

***

https://www.jenkins.io/doc/book/pipeline/

* Access all resources

![](assets/qxQO5HBdBEKJO9HIGo7p0Lg4GXiB4XHnolfFzfkOMSQ=.png)

![](assets/wpxPglNiyHyEkv3oak3GfLbM8CJQY8WzR3MfsFuEk1o=.png)

* Install Pipeline plugin and ssh build plugin

![](assets/l6XgoNBtzuDscKRVngSSBp0jmDaVjzUofML0-TrgvO4=.png)

![](assets/4RqtXQVvc-jGK0MHgIg6ZQHBubThwMwkzkgAim1tizk=.png)

* Create the passwordless ssh

![](assets/-MIpEuuGFTyZSNzSCySqn4FmYOpMbL2XSRlqysOhz2w=.png)

![](assets/yot6g_GncK_BjTh6AXjw-AU6AQy3d34ipqVfaCy4Eus=.png)

* Check the site resource

![](assets/M-X1YU6_cc9S3wTAuVPaqxVn-iq730PgnYjcGZAiM7E=.png)

* Create the agent node

![](assets/vDESTg6TrQYI2OBfF9mUBvPF5LaHR8Oj49l3kOaa8bk=.png)

![](assets/4BQMLlBDBOjXgTaZu6epNirTD8XP-LJsAaaLgRQ0Yvg=.png)

![](assets/hgzrCiCbLMev9YM5vuVvg7rXIy3lQFlSaRwQzgJKtKM=.png)

![](assets/YsftNnUh2YvFwD-qRX1c-0-54-hdo6d7T6MTuP3zGPg=.png)

* Create the Pipeline

![](assets/DH4JujINgJUxPqGazk1pa3wQzcao3-pqrmqappZv-io=.png)

![](assets/ojIIoOkV-uw8xCFx59uuukA-kXSOitqvsppVzQDahzI=.png)

![](assets/n0DXncnWRphu8TtNUMEZRMV2bnBwPLQfjo5gDdTAyPU=.png)

* Run and check

![](assets/ZQpfswWSbUAUEPZlmLwLcrTY4KxfAZRTVT5leSRPwH4=.png)

![](assets/9pnCknsxIAf9HL8x2xCDW7hQ-l-j4m8F_g3zRkY62No=.png)

![](assets/ibBFG3w-I30oiDqAdTooYi_n5htd_AlzdQ1KBHzWpWg=.png)

![](assets/rb0GPkMSFyHLUfE15dDp_XIcJcYi689f6FkEeQ2Ez_s=.png)

