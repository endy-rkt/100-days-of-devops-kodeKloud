# Day 50: Set Resource Limits in Kubernetes Pods

**subjects**

***

The Nautilus DevOps team has noticed performance issues in some Kubernetes-hosted applications due to resource constraints. To address this, they plan to set limits on resource utilization. Here are the details:

Create a pod named`httpd-pod`with a container named`httpd-container`. Use the`httpd`image with the`latest`tag (specify as`httpd:latest`). Set the following resource limits:

Requests: Memory:`15Mi`, CPU:`100m`

Limits: Memory:`20Mi`, CPU:`100m`

`Note:`The`kubectl`utility on the`jump-host`has been configured to work with the Kubernetes cluster.

***

* Check k8s cluster

![](assets/6sgfyYyCppxtCA6f_aTUSY65xbWIfklHdBHgBf_pNfs=.png)

* write yaml file for the pod

![](assets/ixr_KtuJH2cx0A2Y7JCZ29vg_hIGDt9nXqdTgPlO3dc=.png)

* test

![](assets/volYjrRNTUVALxR1-PuxjvWnoS2RaOhjGgnTQMNdCUM=.png)

