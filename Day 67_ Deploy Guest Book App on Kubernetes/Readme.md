# Day 67: Deploy Guest Book App on Kubernetes

**subject**

***

The Nautilus Application development team has finished development of one of the applications and it is ready for deployment. It is a guestbook application that will be used to manage entries for guests/visitors. As per discussion with the DevOps team, they have finalized the infrastructure that will be deployed on Kubernetes cluster. Below you can find more details about it.

`BACK-END TIER`

1. Create a deployment named `redis-master` for Redis master.a.) Replicas count should be `1`.b.) Container name should be `master-redis-nautilus` and it should use image `redis`. c.) Request resources as `CPU` should be `100m` and `Memory` should be `100Mi`.d.) Container port should be redis default port i.e `6379`.
2. Create a service named `redis-master` for Redis master. Port and targetPort should be Redis default port i.e `6379`. 
3. Create another deployment named `redis-slave` for Redis slave. a.) Replicas count should be `2`. b.) Container name should be `slave-redis-nautilus` and it should use `gcr.io/google_samples/gb-redisslave:v3` image.c.) Requests resources as `CPU` should be `100m` and `Memory` should be `100Mi`.d.) Define an environment variable named `GET_HOSTS_FROM` and its value should be `dns`. e.) Container port should be Redis default port i.e `6379`.
4. Create another service named `redis-slave`. It should use Redis default port i.e `6379`.
5. Create another service named `redis-follower`. Port and targetPort should be Redis default port i.e `6379`. Its selector `app` should be `redis-slave`.

`FRONT END TIER`

1. Create a deployment named `frontend`.a.) Replicas count should be `3`. b.) Container name should be `php-redis-nautilus` and it should use `gcr.io/google-samples/gb-frontend@sha256:a908df8486ff66f2c4daa0d3d8a2fa09846a1fc8efd65649c0109695c7c5cbff` image.c.) Request resources as `CPU` should be `100m` and `Memory` should be `100Mi`.d.) Define an environment variable named as `GET_HOSTS_FROM` and its value should be `dns`.e.) Container port should be `80`.
2. Create a service named `frontend`. Its `type` should be `NodePort`, port should be `80` and its `nodePort` should be `30009`.

Finally, you can check the `guestbook app` by clicking on `App` button.

`You can use any labels as per your choice.`

`Note:` The `kubectl` utility on the `jump-host` has been configured to work with the Kubernetes cluster.

***

* Check env

![](assets/jmJMFABVXYjakL0k1dhKiiAXaFwxnSkZ5kX2WRlS_VI=.png)

* Create redis master deployment and service

![](assets/bBlXQ2Kq43ayKC_zfIpwQpbYa9JmQp26D1S3RMdUeUY=.png)

![](assets/a0V0DKugZxw3r-eijUfLWxEfXE2hQoBGoWeJ-b6PkWs=.png)

![](assets/opSyYxJ2vgyG_MG2WcLoQO2wlXIWceTIqsTPjjttlsQ=.png)

* Create redis slave deployment and service

![](assets/_F64lYi29ifvzsbb5GnA-EeRvoC-OYuWrcDBlCh2Mz0=.png)

![](assets/-gkyqGCzFZX-0I-IJECyx8XRBaEn52Irn0KjqrIyh3k=.png)

![](assets/fQ1aLxHA-qVzt0ZJQDeHtoB9AgCtNrlT_xFZeyworWs=.png)

* Create frontend deployment and service

![](assets/FxQXf-pydtRO-J_Bt4ocR7NCwcS6HyPJ_jvJrcNqzd0=.png)

![](assets/JIuY5pkCd40xQFEGNJ_79tpfQDu-nf32kOANHy7jKto=.png)

![](assets/8HW2EsUANLbPLlBQs_ugWN_uDahJ5yIA4aJzFQTGfco=.png)

* Check and test

![](assets/03SdDFxL2QR6kgcQC5c5ZSCZpfEBcXz_2LfpkO9MRWU=.png)

