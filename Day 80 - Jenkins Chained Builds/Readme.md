# Day 80: Jenkins Chained Builds

**subject**

***

The DevOps team was looking for a solution where they want to restart Apache service on all app servers if the deployment goes fine on these servers in Stratos Datacenter. After having a discussion, they came up with a solution to use Jenkins chained builds so that they can use a downstream job for services which should only be triggered by the deployment job. So as per the requirements mentioned below configure the required Jenkins jobs.

Click on the`Jenkins`button on the top bar to access the Jenkins UI. Login using username`admin`and`Adm!n321`password.





Similarly you can access`Gitea UI`on port`3000`(or click the`Gitea`button) and username and password for Git is`sarah`and`Sarah_pass123`respectively. Under user`sarah`you will find a repository named`web`.





Apache is already installed and configured on the app server. The doc root`/var/www/html`on**App Server 1**is a local git repository tracking the origin`web`repository.





1\. Create a Jenkins job named`nautilus-app-deployment`and configure it to pull changes from the`master`branch of the`web`repository on**App Server 1**under`/var/www/html`directory.





2\. Create another Jenkins job named`manage-services`and make it a`downstream job`for`nautilus-app-deployment`. Things to take care about this job are:





a. This job should restart`httpd`service on the app server (App Server 1).



b. Trigger this job only if the`upstream job`i.e`nautilus-app-deployment`is stable.





The LB server is already configured. Click on the`App`button on the top bar to access the app. Please make sure the required content is loading on the main URL (e.g. http://stlb01:8091) i.e there should not be a sub-directory like http://stlb01:8091/web etc.





`Note:`





1\. You might need to install some plugins and restart Jenkins service. So, we recommend clicking on`Restart Jenkins when installation is complete and no jobs are running`on plugin installation/update page i.e`update centre`. Also some times Jenkins UI gets stuck when Jenkins service restarts in the back end so in such case please make sure to refresh the UI page.





2\. Make sure Jenkins job passes even on repetitive runs as validation may try to build the job multiple times.

3\. Deployment related tasks should be done by`sudo`user on the destination server to avoid any permission issues so make sure to configure your Jenkins job accordingly.

4\. For these kind of scenarios requiring changes to be done in a web UI, please take screenshots so that you can share it with us for review in case your task is marked incomplete. You may also consider using a screen recording software such as loom.com to record and share your work.

***

https://upstream-downstream-job.hashnode.dev/understanding-upstream-and-downstream-jobs-in-jenkins

* Access all resources

![](assets/PIdsK1TuOKRHVPBZPPGchI5617KtUxj35at0Guq8QGo=.png)

![](assets/hWK_JQl-G7O8Byx2fv_vvOcKUif4OkbcuN_ZmYcdBp4=.png)

* configure passwordless ssh

![](assets/Ab_jjUYhVNWN7LHOGOsCw6p5jNvh_vZSp7DALfGTm40=.png)

* Configure the app server

![](assets/Gsx5nTtmJo_A4ah6Wu7E2cpmhnMW0WFaLRVwRw8rMFo=.png)

![](assets/IoLzQ6_GmX6Ke0HTajcEL8h9Ky97u-dA6qja9mKHhPs=.png)

* Install jenkins plugin

![](assets/E6V50S4ZKB8ecQdX22QDGjvEz_REewAExNM96pWeD3c=.png)

* Configure node agent

![](assets/JZ6KIEvWWA2z59VzSiNs78MVCsaFd6nT4r_DU9mYkeU=.png)

![](assets/2P8K82J_abnnWSGk_8ZbFJfp-ZRlrQTLR7Z_gojJRiI=.png)

![](assets/Nr8PGqaEv_8_Dyc4NvqRezp4IsDzgDBJvaP8h4AZHfs=.png)

![](assets/m7-LDGOatDBOnmMFnojWRW1b5qFquuFgYHx2o4UpiwE=.png)

* Configure the first job

![](assets/m5BpIRwqnbQgp4BL12U3haJ6P8mNz3rEAr2SmHPRLeE=.png)

![](assets/USc-8qqk8VYztQoHgrUgWJC0trOH7Bdno5q2UwZUjzM=.png)

![](assets/b7uGrdbgp8a3cS3Iqi5zJ8_5VX1-fTYBHJXN68AwWIc=.png)

![](assets/FcqEaUKpGnZwK5A4bhTONDUi37sonvT8YuZMYiJcoPU=.png)

![](assets/U80bi_mVyGjwEgrVDhop_7rUOeiWYs-IvzIqjf6sZ_o=.png)

![](assets/uCr-2hm9VWoXHwsnbedbSifaJ3eH7qwnamg2rVOrkxE=.png)

* Configure second job

![](assets/rZO-7gain3requhNTfzZBeZ5txR0Xqr4BmSUPkckEok=.png)

![](assets/WkFrnIaANe3jiJCv5YqOUEcVTeVB6L7DDO4CXrRb7hU=.png)

* Run and test

![](assets/Tv47up-GeOtOY4fyjKT6czvCazsAAIV3s8xBT20A8rk=.png)

![](assets/6bl1THWB6C8hUFpqFNpX97ZUkLeybsB61MKIDQGNLtc=.png)
