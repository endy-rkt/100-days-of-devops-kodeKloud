# Day 77: Jenkins Deploy Pipeline

**subject**

***

The development team of xFusionCorp Industries is working on to develop a new static website and they are planning to deploy the same on Nautilus App Server using Jenkins pipeline. They have shared their requirements with the DevOps team and accordingly we need to create a Jenkins pipeline job. Please find below more details about the task:

Click on the `Jenkins` button on the top bar to access the Jenkins UI. Login using username `admin` and password `Adm!n321`.

Similarly, click on the `Gitea` button on the top bar to access the Gitea UI. Login using username `sarah` and password `Sarah_pass123`. There under user `sarah` you will find a repository named `web_app` that is already cloned on **App Server 1** under `/var/www/html`. sarah is a developer who is working on this repository.

1. Add a slave node named `App Server 1`. It should be labeled as `stapp01` and its remote root directory should be `/home/sarah/jenkins_agent` (the repository is cloned under `/var/www/html`; the agent uses a separate directory so it does not pollute the repo).
2. We have already cloned repository on **App Server 1** under `/var/www/html`.
3. Apache is already installed on the app server and is running on port `8080`.
4. Create a Jenkins pipeline job named `xfusion-webapp-job` (it must not be a `Multibranch pipeline`) and configure it to:
   * Deploy the code from `web_app` repository under `/var/www/html` on **App Server 1**, as this is the document root of the app server. The pipeline should have a single stage named `Deploy` ( which is case sensitive ) to accomplish the deployment.

LB server is already configured. You should be able to see the latest changes you made by clicking on the `App` button. Please make sure the required content is loading on the main URL `https://<LBR-URL>` i.e there should not be a sub-directory like `https://<LBR-URL>/web_app` etc.

`Note:`

1. You might need to install some plugins and restart Jenkins service. So, we recommend clicking on `Restart Jenkins when installation is complete and no jobs are running` on plugin installation/update page i.e `update centre`. Also, Jenkins UI sometimes gets stuck when Jenkins service restarts in the back end. In this case, please make sure to refresh the UI page.
2. For these kind of scenarios requiring changes to be done in a web UI, please take screenshots so that you can share it with us for review in case your task is marked incomplete. You may also consider using a screen recording software such as loom.com to record and share your work.

***

https://www.jenkins.io/doc/book/pipeline/

* Check all base plateform: jenkins, git

![](assets/89IZhprkpxykabgtnBUrD-waHpVcKtgrD8MjNYl7OPM=.png)

![](assets/B9ogyKQOm2IAizwxzCfRNn-4j3VqcpBfZH3Iw5uwBNM=.png)

* Create ssh passwordless connection

![](assets/QJszmv55SDUP5VKGhPhBkIfGf_69okSaqXUZEKl0N3w=.png)

![](assets/EiHA0VGs78JwSASzxBf9O6Dy_tMt5gBAw-svJLCt1tA=.png)

* Create slave node

![](assets/V7o7skh6_ccW4t1wYm-et014kzhaNQ7ZxgvE4Al_7Fk=.png)

![](assets/er0o-Fpos-SePH-uINIFW1_-sFOXbbyb68tqS8gSZDU=.png)

![](assets/W1ngOxjqdJcL2LFaSfzuTFLrXodVcl1u9ALCe5eZ7qg=.png)

* Check the existant project on the agent

![](assets/ttaNkX1uRneJJ7Dln1hdAtTpX2ZsrSpVCbZtuvH-Imc=.png)

![](assets/t6WVhA9eDulOrzc8Xh3JEV4nVVLMXhw4XZhVXsWcE2M=.png)

* Create the Pipeline

![](assets/Fq7www3BMGxbDGCwl3Y8R-Y3tme3d8H7uD0P_hjXXyc=.png)

![](assets/PdsLkZyZoV7C54cSTrHjOhDqlmue3zIL7WjwOzXtarg=.png)

![](assets/u7VPA5nIRxoUChOPo7MLyhLtbjbxhswJBMhgCExKg1E=.png)

* Test the pipeline 

![](assets/boAcKGG7WhFGgor59q347VPpY644T_Ahhd8eYFF-iuE=.png)

![](assets/Hy_duFTb2HwciZv-PutY0yl0XnDKGbXg6k9YvZhPQR8=.png)
