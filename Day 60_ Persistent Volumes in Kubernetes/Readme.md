# Day 60: Persistent Volumes in Kubernetes

**subject**

***

The Nautilus DevOps team is working on a Kubernetes template to deploy a web application on the cluster. There are some requirements to create/use persistent volumes to store the application code, and the template needs to be designed accordingly. Please find more details below:

1. Create a`PersistentVolume`named as`pv-devops`. Configure the`spec`as storage class should be`manual`, set capacity to`5Gi`, set access mode to`ReadWriteOnce`, volume type should be`hostPath`and set path to`/mnt/finance`(this directory is already created, you might not be able to access it directly, so you need not to worry about it).
2. Create a`PersistentVolumeClaim`named as`pvc-devops`. Configure the`spec`as storage class should be`manual`, request`2Gi`of the storage, set access mode to`ReadWriteOnce`.
3. Create a`pod`named as`pod-devops`, mount the persistent volume you created with claim name`pvc-devops`at document root of the web server, the container within the pod should be named as`container-devops`using image`nginx`with`latest`tag only (remember to mention the tag i.e`nginx:latest`).
4. Create a node port type service named`web-devops`using node port`30008`to expose the web server running within the pod.

`Note:`The`kubectl`utility on the`jump-host`has been configured to work with the Kubernetes cluster.

***

https://blog.stephane-robert.info/docs/conteneurs/orchestrateurs/kubernetes/storage/

https://kubernetes.io/docs/concepts/storage/persistent-volumes/

* Check the cluster

![](assets/BwMaw68TH2v1yo5sJbXWyg2abmcn8s0iYQzZtGq0l5w=.png)

* Create the pv and pvc

![](assets/KLZAOdqCLkzOn4EDi6wfXvkAv3ku8rOZ3G3RbpjFcWU=.png)

* Create the pod and service

![](assets/T2diDjBZtGwOX02NnQLcrOnodQbAr1-374ErgyNLtic=.png)

* Run and test

![](assets/wuXaObmJVVePG-8TAh3vVqz-52gpyZ-vuvrCLfBflv0=.png)

![](assets/ec_9u3cUZVtal7Cd8Sh823MoohUDiejVb_4gjprFwDs=.png)
