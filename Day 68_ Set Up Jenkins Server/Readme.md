# Day 68: Set Up Jenkins Server

**subject**

***

The DevOps team at xFusionCorp Industries is initiating the setup of CI/CD pipelines and has decided to utilize Jenkins as their server. Execute the task according to the provided requirements:

1\. Install`Jenkins`on the jenkins server using the`apt`utility only, and start it using the`service`command.

* If you face a timeout issue while starting the Jenkins service, first check the service status with`service jenkins status`
* Then review the logs in`/var/log/jenkins/jenkins.log`to identify the cause.

2\. Jenkin's admin user name should be`theadmin`, password should be`Adm!n321`, full name should be`Siva`and email should be`siva@jenkins.stratos.xfusioncorp.com`.

`Note:`

1\. To access the`jenkins`server, connect from the jump host using the`root`user with the password`S3curePass`.

2\. After Jenkins server installation, click the`Jenkins`button on the top bar to access the Jenkins UI and follow on-screen instructions to create an admin user.

***

https://www.jenkins.io/doc/book/installing/linux/

https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-22-04

* ssh into the jenkins server

![](assets/yLKF8N8DGBbxrpuRW1HUWL7ZqEMwiQY23MzjUn6GHpA=.png)

* Setup environment before installation

![](assets/hPxFhTRcdPSeXjecDiMHfT9y6cpVZCEI5iZ3M_XWy2E=.png)

* Check the java version used

![](assets/IVBvtlBbpU0c_TBGbjI8YFOfMzBupP-tH_KA8ZzJh1A=.png)

* Install jenkins

![](assets/vxx6DKgv6gx9HmAghRaS29rIxTCkfAtBcRMHGmxaEPY=.png)

![](assets/bVcjAMtTcFDrr2Zcbase5-o_Qtg564nNLN8wXMXUCSk=.png)

* Start jenkins

![](assets/xBOF9hrK3rzJssGwuA0j0lXVtlSkCMkR1d_8apQxu34=.png)

* run  and config

![](assets/t1tNm-ECSyMjEDfEI80e3DeacBRiHQzU4ExX3yRYBF8=.png)

![](assets/8K3bAsXJUDP14I8G0lkM6zzzGEbK4D8-iM_H-1wshuY=.png)

![](assets/ohWS4c29KKd-LASn_Mdkg9ZYyu_SLLyW0rJpwr-Mp3g=.png)

![](assets/-Qozz_-dUS5WmQo9yS6QTkGzF-kSp-pGTGODWiwsYD4=.png)

* Test 

![](assets/vuYMzB03gsxcn5i4hVfPlsPu6CUZ0xPALvPlG8v5OgU=.png)

![](assets/r8W79oeU5Y9S6WeEFCRZsTDmCUXlMEtOXmSHsGXvH28=.png)
