# Day 81: Jenkins Multistage Pipeline

**subject**

***







The development team of xFusionCorp Industries is working on to develop a new static website and they are planning to deploy the same on Nautilus App Server using Jenkins pipeline. They have shared their requirements with the DevOps team and accordingly we need to create a Jenkins pipeline job. Please find below more details about the task:









Click on the `Jenkins` button on the top bar to access the Jenkins UI. Login using username `admin` and password `Adm!n321`.





Similarly, click on the `Gitea` button on the top bar to access the Gitea UI. Login using username `sarah` and password `Sarah_pass123`.





There is a repository named `sarah/web` in Gitea that is already cloned on **App Server 1** under `/var/www/html` directory.





1. Update the content of the file `index.html` under the same repository to `Welcome to xFusionCorp Industries` and push the changes to the origin into the `master` branch.


2. Apache is already installed on the app server and is running on port `8080`.


3. Add **App Server 1** as a Jenkins agent (slave) node: name `App Server 1`, label `stapp01`, remote root directory `/home/sarah/jenkins_agent`, launch via SSH with host `stapp01` and credentials for user `sarah`. Install `java-17-openjdk` on App Server 1 if needed.


4. Create a Jenkins pipeline job named `deploy-job` (it must not be a `Multibranch pipeline` job) and pipeline should have two stages `Deploy` and `Test` ( names are case sensitive ). Configure these stages as per details mentioned below. 

   a. The `Deploy` stage should deploy the code from `web` repository under `/var/www/html` on **App Server 1**, as this is the document root of the app server.

   b. The pipeline should run on the **App Server 1** node (e.g. use label `stapp01`).

   c. The `Test` stage should just test if the app is working fine and website is accessible. Its up to you how you design this stage to test it out, you can simply add a `curl` command as well to run a curl against the LBR URL (`http://stlb01:8091`) to see if the website is working or not. Make sure this stage fails in case the website/app is not working or if the `Deploy` stage fails.



Click on the `App` button on the top bar to see the latest changes you deployed. Please make sure the required content is loading on the main URL `http://stlb01:8091` i.e there should not be a sub-directory like `http://stlb01:8091/web` etc.





`Note:`





1. You might need to install some plugins and restart Jenkins service. So, we recommend clicking on `Restart Jenkins when installation is complete and no jobs are running` on plugin installation/update page i.e `update centre`. Also, Jenkins UI sometimes gets stuck when Jenkins service restarts in the back end. In this case, please make sure to refresh the UI page.


2. For these kind of scenarios requiring changes to be done in a web UI, please take screenshots so that you can share it with us for review in case your task is marked incomplete. You may also consider using a screen recording software such as loom.com to record and share your work.

***

* Access all resources

![](assets/stTnWFaPpgBGzTpjd-_SkoOYC1-lLayzaw0ej-qBWyY=.png)

![](assets/Q3TeGiGPvSXJNTMHckcXBiLWVqQBUv8pLulce1A8n8Y=.png)

* Setup passwordless ssh

![](assets/1O9eY1kftHON8qOaFyqK_2pDBYGEs2loeJJvVqA3s_k=.png)

* Setup the app server 01

![](assets/4c6_SlXQBbgxlkwkLOfWnBwZ-k5YKc9UWOWthKX5Frw=.png)

* Install jenkins plugins

![](assets/C2M8vSxrgyRn6OrFLGKTI9cUzK_Tio0zrY5_TxOCHxE=.png)

* Setup node agent

![](assets/nfHVaGdiaEVl2vvVxAptNVzGH7P5xuln5gHaxQKaF3w=.png)

![](assets/1pIAIo19FoTnBgrpbH2lUqu7Szc049G46LRg3m4asI4=.png)

![](assets/CjNQxkjXrGzAzGweNvXyFTQAiWAExbGcV6QV8_jCq3s=.png)

![](assets/xjnqh1fNHl504JHmTXt5-rE8_p2uQaYpHBK4ZsyYvu4=.png)

![](assets/Rc5AJIsnqkpYbCg9ebZwNvhdhUYYeScb7JacRLZY12E=.png)



* Create the job

![](assets/St40VeF9yBD_DC8X0AO2LHaAB9Pqhg9Ij6OK7nIkCVg=.png)

![](assets/ddBsliZUOcld20pl0kCKba98N3_j3jBsPZUaY_XSunM=.png)

![](assets/rT5ghq9Nk06QlblBE8UXScTVmOoWxBce4oSwM9fw7X0=.png)

* Run ad test

![](assets/S7JPr5dz7S8Ipn6dT2x4m1qwHYLDGXiQIvCpMiEYypk=.png)

![](assets/4re3cRj1CrMa7DMbhIsxUgYk14pgELCLIIpEA8MRADI=.png)

![](assets/VXq8hiNZOpZyQO-R_xg7j6zTOKKx5aJyCHPbJNMmoyY=.png)
